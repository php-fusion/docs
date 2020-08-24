---
description: >-
  In this section, we should take a look into how the administration should work
  and carefully plan it too ensure there are no user experience interferences.
---

# Administrative view

### Listing of all property records

For this part, we will start with a php function `property_listing()` which will return the HTML table data of all the real estate property records. 

#### Model for getting data entries

For data source, we will use a function, lets call it `db_property_data()` to grab SQL records for display and store them into an array. If there are no records we shall return an empty array. Here, we also need to limit our SQL query with `$_GET['rowstart']` to avoid huge data query and long processing time, and let's put the limit of output to **20** for this tutorial purposes.  

```php
// Build the model - data source
function db_property_data($id = 0, $limit = 20) {
    // empty rows
    $data = array();

    // If ID is present
    if (isnum($id) && $id) {
        $query = "SELECT * FROM ".DB_PROPERTY." WHERE property_id=:id";
        $param = array(":id" => (int)$id);
        $result = dbquery($query, $param);
        if (dbrows($result)) {
            return dbarray($result);
        }
        return $data;
    }

    // If ID is not present, list out everything.
    $total_rows = get_property_total_count();
    $rowstart = get_rowstart("rows", $total_rows);
    $query = "SELECT * FROM ".DB_PROPERTY." ORDER BY property_id LIMIT $rowstart, $limit";
    $result = dbquery($query);
    if (dbrows($result)) {
        if ($total_rows > $limit) {
            // When we use the below function, it will set the cache navigation status value to true.
            set_property_nav_status();
        }
        while ($rows = dbarray($result)) {
            $data[$rows["property_id"]] = $rows;
        }
    }

    return (array)$data;
}

```

There are a few custom functions in our `db_property_data` function. They are as the following:

**Getting the count of total entries function** - `get_property_total_count()`

```php
// get the total count for the current database
function get_property_total_count() {
    static $count_result = 0;
    if (empty($count_result)) {
        $count_result = (int)dbresult(dbquery("SELECT count(property_id) 'count' FROM ".DB_PROPERTY), 0);
    }
    return $count_result;
}
```

Two function to set and get static **cache** to indicate whether a pagination is needed. This is done through `set_property_nav_status()` and `get_property_nav_status()` function. When the `$total_rows` is more than `$limit` we will call the setter to the static variable `$navigation_status` as **true**.

```php
// Since the data model function ran before hand, the set_property_nav_status should be true if rows are more.
function get_property_nav_status($limit = 20) {
    // Let's begin
    if (set_property_nav_status() === TRUE) {
        $total_rows = get_property_total_count();
        $rowstart = get_rowstart("rows", $limit);
        if ($total_rows > $rowstart) {
            return makepagenav($rowstart, $limit, $total_rows, 3, FORM_REQUEST."&rowstart=", "rows");
        }
    }
    return "";
}

// Set the property navigation
function set_property_nav_status() {
    static $navigation_status = FALSE;
    if (empty($navigation_status)) {
        $navigation_status = TRUE;
    }
    return $navigation_status;
}
```

#### View function to display the HTML

```php
function property_listing() {

    echo "<div class='text-right'>";
    echo get_property_nav_status();
    echo "</div>";
    // Property listing columns
    echo "<table class='table'>";
    echo "<thead><tr><th>".$locale["PROP_0200"]."</th><th>".$locale["PROP_0201"]."</th><th>".$locale["PROP_0202"]."</th><th>".$locale["PROP_0203"]."</th><th>".$locale["PROP_0204"]."</th></tr></thead><tbody>";
    if (!empty($data)) {
        foreach ($data as $rows) {
            // Coding standard
            // Do not implement any if/else conditions within loop. It will increase code complexity count immensely.
            // Instead, implements conditions process in private functions.
            $edit_link = clean_request("action=edit&id=".$rows["property_id"], array("action", "id"), FALSE);
            $del_link = clean_request("action=del&id=".$rows["property_id"], array("action", "id"), FALSE);
            $view_link = clean_request("action=view&id=".$rows["property_id"], array("action", "id"), FALSE);
            echo "<tr>";
            // property name and actions
            echo "<td>";
            echo "<div class='display-flex-row'>";
            echo "<div class='icon-sm'>".listing_thumbnail($data)."</div>";
            echo "<div>";
            echo "<a href='$edit_link' aria-describedby='edit'>".$data["property_name"]."</a>";
            echo "<div><a href='$edit_link'>".$locale["edit"]."</a> - <a href='$del_link'>".$locale["delete"]."</a> - <a href='$view_link'>".$locale["view"]."</a>";
            echo "</div>";
            echo "</div>";
            echo "</td>";
            // status
            echo "<td>".listing_status($rows["property_stats"])."</td>";
            // date
            echo "<td>".showdate("longdate", $rows["property_datestamp"])."</td>";
            // access
            echo "<td>".getgroupname($rows["property_access"])."</td>";
            // id
            echo "<td>".$rows["property_id"]."</td>";
            echo "</tr>";
        }
    } else {
        echo "<tr><td colspan='5'>".$locale["PROP_0400"]."</td></tr>";
    }
    echo "</tbody></table>";
}
```

As you can see, the above code has two more custom function, `listing_status()` and `listing_thumbnail()` to return the appropriate values.

```php
// Private function - return the listing status
function listing_status($status) {
    $locale = fusion_get_locale();
    $choices = array($locale["PROP_0206"], $locale["PROP_0207"]);
    if (isset($choices[$status])) {
        return $choices[$status];
    }
    return 0;
}

// Private function - check for thumbs
function listing_thumbnail($data) {
    $thumbnail = get_image("imagenotfound");
    if (file_exists(PROPERTY_IMAGES.$data["property_thumbnail"])) {
        $thumbnail = "<img src='".PROPERTY_IMAGES.$data["property_thumbnail"]."' alt=''/>";
    }
    return $thumbnail;
}
```

### Input form to add, edit or delete entry

We will need another function to host the form display when an administrator clicks the add new button or edit link in the property listing table. `property_listing()`

```php
// Form UI
function property_form() {
    // Get locale    
    $locale = fusion_get_locale();

    // Default data or Callback data
    $data = get_default_form_data();
    if (post("submit")) {
        // Post submissions and return of data in case of error
        $data = handle_form_data();
    }

    echo "<div class='row'>";
    // Set column width for all device type
    echo "<div class='".grid_column_size(100, 100, 100, 50)."'>";
    // add form open tag and CSRF token.
    echo openform("postform", "POST", FORM_REQUEST, array("enctype" => TRUE));
    // add property name text field
    echo form_text("property_name", $locale["PROP_0200"], $data["property_name"], array("required" => TRUE));
    // adds tinymce textarea
    echo form_textarea("property_description", "", $data["property_description"], array("required" => TRUE, "placeholder" => $locale["PROP_0205"], "tinymce" => TRUE, "form_id" => "postform"));
    // add an image input
    echo form_fileinput("property_image", "", $data["property_image"], array(
        "upload_path" => PROPERTY_IMAGES,
        "thumbnail"   => TRUE,
        "thumbnail_w" => 500,
        "thumbnail_h" => 500,
        "croppie"     => FALSE,
    ));
    // add active selector
    echo form_select("property_status", $locale["PROP_0201"], $data["property_status"], array("options" =>array($locale["PROP_0206"], $locale["PROP_0207"])));
    // add submit button
    echo form_button("property_submit", $locale["PROP_0208"], "submit", array("class"=>"btn-primary"));
    // close form tag
    echo closeform();
    echo "</div>";

}

```

The above form components is generated with [**Fusion Dynamics Libraries**](../../phpfusion-codex/dynamics/) ****which interacts with `sanitizer()`to process data validation. 

{% hint style="info" %}
We've eliminated the complexity of sanitization, and standardized it with the same function for all kinds of value types - email, URI, texts, numbers, image and file upload, and more. For more information on this topic, please read the [**Fusion Dynamics Libraries**](../../phpfusion-codex/dynamics/) ****documentation.
{% endhint %}

```php
// Private function - handle the form submission.   
function handle_form_data() {
    $userdata = fusion_get_userdata();
    $locale = fusion_get_locale();
    // Xdebug start
    $data = array(
        "property_id"          => sanitizer("property_id", 0, "property_id"),
        "property_name"        => sanitizer("property_name", "", "property_name"),
        "property_description" => sanitizer("property_description", "", "property_description"),
        "property_datestamp"   => time(),
        "property_image"       => "",
        "property_thumb"       => "",
        "property_status"      => sanitizer("property_status", "", "property_status"),
        "property_user"        => $userdata["user_id"],
        "property_access"      => sanitizer("property_access", "", "property_access"),
    );
    // If the above sanitization has no error, proceed
    if (fusion_safe()) {
        // start to sanitize the fileinputs
        $upload = file_sanitizer("property_image", "", "property_image");
        // when upload has no error, proceed
        if (fusion_safe()) {
            if (isset($upload["error"]) && !$upload["error"]) {
                $data["property_image"] = $upload["image_name"];
                $data["property_thumb"] = $upload["image_thumb"];
            }
        }
        //print_p($data);
        // Xdebug stop
        // If upload has no problem, proceed to store data with $data values.
        if (fusion_safe()) {
            $mode = "save";
            $message = $locale["PROP_0301"];
            if ($data["property_id"]) {
                // If ID exist, this means it's an update
                $mode = "update";
                $message = $locale["PROP_0300"];
            }
            // Insert or update a record, MYSQL syntax is automated.
            // But on "save" mode, this function will return lastinsertid();
            dbquery_insert(DB_PROPERTY, $data, $mode);
            // display system message
            add_notice("success", $message);
            // At this point, we do not know the real URL address yet since the controller has not been coded yet.
            // but there is one thing we do know - when $_GET['action'] and $_GET['id'] is present, the form is shown
            // Using clean request, we are sure to strip these 2 $_GET keys from current page return url, therefore, exiting the form view.
            $exit_link = clean_request("", array("action", "id"), FALSE);
            redirect($exit_link);
        }
    }

    return (array)$data;
}    
```

```php
// Private function - get default callback data.
function get_default_form_data() {
    // default data
    $data = array(
        "property_id"          => 0,
        "property_name"        => "",
        "property_description" => "",
        "property_datestamp"   => time(),
        "property_image"       => "",
        "property_thumb"       => "",
        "property_status"      => 0,
        "property_user"        => fusion_get_userdata("user_id"), // Your own user id
        "property_access"      => USER_LEVEL_PUBLIC,
    );

    $id = get_current_id();
    if (isnum($id) && $id > 0) {
        if ($data = db_property_data($id)) {
            redirect(clean_request("", array("action", "id"), FALSE));
        }
    }

    return (array)$data;
}
```

```php
// Private function get ID.
function get_current_id() {
    $id = 0;
    // if current action is edit or delete
    if (in_array(get("action"), array("edit", "del"))) {
        $id = (int)get("id", FILTER_VALIDATE_INT);
    }
    return (int)$id;
}
```

### View controller

