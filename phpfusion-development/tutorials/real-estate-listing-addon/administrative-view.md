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

There are a few custom functions in our db\_property\_data function. They are as the following:

**Getting the count of total entries** - `get_property_total_count()`

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



### View controller

