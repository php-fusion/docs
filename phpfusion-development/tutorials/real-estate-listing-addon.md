---
description: >-
  In this tutorial, we will be making a custom inventory database for real
  estate listing that you can install into PHP-Fusion 9.
---

# Real Estate Listing Addon

**Time to complete tutorial** - Less than 1 hour.

### **In this tutorial, we will be discovering** 

  
****1. The basic of form handling in version 9  
2. The basic of SQL query in version 9  
3. Using PHP-Fusion utility functions such as theme and infusion components to assist you with development of this web application.   
4. Basic concepts of MVCT.   
5. The basics of locale in version 9  
6. The basic SDK to follow to make your work into a custom infusion application package.  
7. Coding it clean with proper coding standard

## **Lets get started.**

First, we will need a name for our project. I'll have the liberty of naming this project for you, but feel free to customize it to your own name. For now, let's call this application - "property". So let's prepare the files as following for the most basic setup.

```text
/property/
- /admin/
----- index.php
----- listing.php
- /locale/
----- index.php
----- English.php
- /templates/
----- index.php
----- public.php
- view.php
- infusion.php
- infusion_db.php
- index.php
```

{% hint style="danger" %}
By placing `index.php` files in every folder, you will be disabling anyone from viewing your files directly via the browser. This is a very important thing that you must remember to do every time you create a folder. Please make it a habit!
{% endhint %}

### Database Structure

Since the property listing will need to be stored somewhere, we will be using the primary MYSQL database as a medium for information data storage. Let's decide our table name and structure as following:

{% tabs %}
{% tab title="Table Structure" %}
**Name**: property

| Table Name | Type / Length | Remarks |
| :--- | :--- | :--- |
| property\_id | BIGINT\(20\) | AUTO INCREMENT |
| property\_name | VARCHAR\(100\) | NOT NULL |
| property\_description | TEXT | NOT NULL |
| property\_image | VARCHAR\(200\) | NOT NULL |
| property\_thumb | VARCHAR\(200\) | NOT NULL |
| property\_datestamp | INT\(10\) | UNSIGNED NOT NULL |
| property\_status | TINYINT\(1\) | UNSIGNED NOT NULL |
| property\_access | SMALLINT\(10\) | NOT NULL |
{% endtab %}

{% tab title="Infusion API" %}
Refer to the **Adding infusion package: Installer API** section below for the file
{% endtab %}

{% tab title="SQL " %}

{% endtab %}
{% endtabs %}

{% hint style="info" %}
You can click on the tab for the corresponding formats that can be used to build the table. I will not explain the SDK in general. Please read the [Infusion SDK](../infusion-sdk.md) for more information on the API.
{% endhint %}

### Defining Infusion Package

We'll begin by defining all the system variables and information defining the package that we will use in the rest of the addon project files in `infusion_db.php`

{% hint style="warning" %}
All `infusion_db.php` file in every folder within /infusions/ folder is automatically loaded by PHP Fusion. As such, there is no need to load this file in any file.
{% endhint %}

{% tabs %}
{% tab title="Installer API" %}
{% code title="infusion.php" %}
```php
<?php
(defined("IN_FUSION")||exit);

// Package information
$inf_title = $locale["PROP_0100"];
$inf_description = $locale["PROP_0101"];
$inf_version = "1.0";
$inf_developer = "Your Name";
$inf_email = "your@email.com"; 
$inf_weburl = "https://your-url.com";
$inf_folder = "property";
$inf_image = "icon.svg";

// Define table structure
$inf_newtable[] = DB_PROPERTY." (
    property_id bigint(20) unsigned not null auto_increment,
	  property_name varchar(100) not null,
		property_description text not null,
		property_image varchar(200) not null,
		property_thumb varchar(200) not null,
		property_datestamp int(10) unsigned not null default '0',
		property_status tinyint(1) unsigned not null default '0',
		property_access smallint(10) not null default '0',		
		PRIMARY KEY (property_id),
		KEY (property_status)
) ENGINE = MYISAM;";

// Adds and remove administrative link
$inf_adminpanel[] = array(
    "title"  => $inf_title,
    "image"  => $inf_image,
    "panel"  => "admin/listing.php",
    "rights" => $inf_rights,
    "language" => LANGUAGE
);

// Drop table when uninstalling
$inf_droptable[] = DB_PROPERTY;

```
{% endcode %}

This file consists of package information in a standard variable required by the infusion installer system. 

The `$inf` array defines table structure the data column structure for the installer to create table as defined. 
{% endtab %}

{% tab title="Package Definitions" %}
{% code title="infusion\_db.php" %}
```php
<?php
(defined("IN_FUSION")||exit);

// Define folder path constant
const PROPERTY = INFUSIONS."property/";

// Defines language folder path constant
const PROPERTY_LOCALESET = PROPERTY."locale/";

// Defines The MYSQL table name constant
const DB_PROPERTY = DB_PREFIX."property";

set_property_locale();

// Function to add property locale file into system cache
function set_property_locale() {
   if (!defined("PROPERTY_LOCALE")) {
        // we begin with english
        $locale = PROPERTY_LOCALE."English.php";
        // find if current user language file is available.
        if (file_exists(PROPERTY_LOCALE.LOCALESET.".php")) {
           $locale = PROPETY_LOCALE.LOCALESET.".php";
        }
        // define a constant
         define("PROPERTY_LOCALE", $locale);
    }    
    // add all variables of the file into the system locale
    fusion_get_locale("", array(PROPERTY_LOCALE));   
}

```
{% endcode %}

This file defines the **CONSTANTS** in the system and **set the system locale.**
{% endtab %}

{% tab title="Locale file" %}
{% code title="/locale/English.php" %}
```php
$locale["PROP_0100"] = "Property Estate";
$locale["PROP_0101"] = "Property Estate Listing Tutorial";
```
{% endcode %}
{% endtab %}
{% endtabs %}

### Administrative View

Now we will proceed to build the administrative interface. The following files are used to build the listing, and the form section for administrative users to manage the property listing in our addon package.

{% tabs %}
{% tab title="/admin/listing.php" %}
{% code title="/admin/listing.php" %}
```php
<?php
require_once __DIR__."/../maincore.php";
require_once THEMES."templates/header.php";

// List UI
function property_listing() {
    $locale = fusion_get_locale();
    
    
}

// Property data
function get_property_data($id = 0) {
}

// Form UI
function property_form() {
    $locale = fusion_get_locale();
}


require_once THEMES."templates/footer.php";
```
{% endcode %}
{% endtab %}

{% tab title="/locale/English.php" %}
{% code title="/locale/English.php" %}
```php
$locale["PROP_0100"] = "Property Estate";
$locale["PROP_0101"] = "Property Estate Listing Tutorial";
```
{% endcode %}
{% endtab %}
{% endtabs %}

### Guest and Member View

