---
description: >-
  These documents contains the basic set of guidelines we want people to follow
  when programming for PHP-Fusion.Coding Standards improves the readability of
  Code.
---

# Coding Standards

## Coding Standards for Infusions

The Basic structure of infusion.php file is like:

```php
<?php
/-------------------------------------------------------+
| PHP-Fusion Content Management System
| Copyright (C) PHP-Fusion Inc
| https://www.php-fusion.co.uk/
+--------------------------------------------------------+
| Filename: infusion.php
| Author: Nick Jones (Digitanium)
| Co-Author: PHP-Fusion Infusion Development Team
+--------------------------------------------------------+
| This program is released as free software under the
| Affero GPL license. You can redistribute it and/or
| modify it under the terms of this license which you
| can read by viewing the included agpl.txt or online
| at www.gnu.org/licenses/agpl.html. Removal of this
| copyright header is strictly prohibited without
| written permission from the original author(s).
+--------------------------------------------------------/
if (!defined("IN_FUSION")) { die("Access Denied"); }
include INFUSIONS."shoutbox_panel/infusion_db.php";
// Check if a locale file is available that match the selected locale.
if (file_exists(INFUSIONS."shoutbox_panel/locale/".LANGUAGE.".php")) {
// Load the locale file matching selection.
include INFUSIONS."shoutbox_panel/locale/".LANGUAGE.".php";
} else {
// Load the default locale file.
include INFUSIONS."shoutbox_panel/locale/English.php";
}
// Infusion general information
$inf_title = $locale['SB_title'];
$inf_description = $locale['SB_desc'];
$inf_version = "1.00";
$inf_developer = "PHP Fusion Development Team";
$inf_email = "";
$inf_weburl = "https://www.php-fusion.co.uk";;
$inf_folder = "shoutbox_panel"; // The folder in which the infusion resides.
//Administration panel
$inf_adminpanel[1] = array("title" => $locale['SB_admin1'], "image" => "shout.gif", "panel" => "shoutbox_admin.php","rights" => "S");
//Multilanguage table for Administration
$inf_mlt[1] = array("title" => $locale['SB_title'], "rights" => "SB");
// Delete any items not required below.
$inf_newtable[1] = DB_SHOUTBOX." (
shout_id MEDIUMINT(8) UNSIGNED NOT NULL AUTO_INCREMENT,
shout_name VARCHAR(50) NOT NULL DEFAULT '',
shout_message VARCHAR(200) NOT NULL DEFAULT '',
shout_datestamp INT(10) UNSIGNED NOT NULL DEFAULT '0',
shout_ip VARCHAR(45) NOT NULL DEFAULT '',
shout_ip_type TINYINT(1) UNSIGNED NOT NULL DEFAULT '4',
shout_hidden TINYINT(1) UNSIGNED NOT NULL DEFAULT '0',
shout_language VARCHAR(50) NOT NULL DEFAULT '',
PRIMARY KEY (shout_id),
KEY shout_datestamp (shout_datestamp)
) ENGINE=MyISAM;";
//Infuse insertations
$inf_insertdbrow[1] = DB_PANELS." (panel_name, panel_filename, panel_content, panel_side, panel_order, panel_type, panel_access, panel_display, panel_status) VALUES('".$locale['SB_title']."', 'shoutbox_panel', '', '4', '3', 'file', '0', '0', '1')";
$inf_insertdbrow[2] = DB_SETTINGS_INF." (settings_name, settings_value, settings_inf) VALUES('visible_shouts', '5', '".$inf_folder."')";
$inf_insertdbrow[3] = DB_SETTINGS_INF." (settings_name, settings_value, settings_inf) VALUES('guest_shouts', '0', '".$inf_folder."')";
//Defuse cleaning $inf_droptable[1] = DB_SHOUTBOX; $inf_deldbrow[1] = DB_PANELS." WHERE panel_filename='".$inf_folder."'"; $inf_deldbrow[2] = DB_SETTINGS_INF." WHERE settings_inf='".$inf_folder."'";
```

Usually the infusion\_db.php file is used to define constants for Database Table names, which are used by the Infusion programmer in various files of the infusion. Its basic contents are like:

```php
<?php
/-------------------------------------------------------+
| PHP-Fusion Content Management System
| Copyright (C) PHP-Fusion Inc
| https://www.php-fusion.co.uk/
+--------------------------------------------------------+
| Filename: infusion_db.php
| Author: PHP Fusion Development Team
+--------------------------------------------------------+
| This program is released as free software under the
| Affero GPL license. You can redistribute it and/or
| modify it under the terms of this license which you
| can read by viewing the included agpl.txt or online
| at www.gnu.org/licenses/agpl.html. Removal of this
| copyright header is strictly prohibited without
| written permission from the original author(s).
+--------------------------------------------------------/
if (!defined("IN_FUSION")) { die("Access Denied"); }
if (!defined("DB_SHOUTBOX")) { define("DB_SHOUTBOX", DB_PREFIX."shoutbox"); } ?>
```

When you are creating your own Infusion, you may need your own tables in the database. Here you will get to know, how to create tables, drop tables, insert rows, delete rows in your own custom tables.

**Creating Tables**

You can create tables in the Database in the infusion.php file as: \(Example\)

```php
$inf_newtable[] = DB_SHOUTBOX." (
    shout_id MEDIUMINT(8) UNSIGNED NOT NULL AUTO_INCREMENT,
    shout_name VARCHAR(50) NOT NULL DEFAULT '',
    shout_message VARCHAR(200) NOT NULL DEFAULT '',
    shout_datestamp INT(10) UNSIGNED NOT NULL DEFAULT '0',
    shout_ip VARCHAR(45) NOT NULL DEFAULT '',
    shout_ip_type TINYINT(1) UNSIGNED NOT NULL DEFAULT '4',
    shout_hidden TINYINT(1) UNSIGNED NOT NULL DEFAULT '0',
    PRIMARY KEY (shout_id),
    KEY shout_datestamp (shout_datestamp)
) ENGINE=MyISAM;";
```

Here, DB\_SHOUTBOX is the constant which holds the Table name in the Database, say, table\_prefix\_shoutbox. And the information like shout\_id, shout\_name etc are the fields and its attributes in the table. $inf\_newtable\[1\] represents that it is the 1st table you want to Create. So, if you want to Create more tables, then you have to create more variables like: 

$inf\_newtable\[\]

$inf\_newtable\[\]

 and so on…

These Tables are created in the Database, when Infusing the infusion.

**Dropping Tables**  
When you have Created Tables, so you must also specify the tables to be Dropped at the time of Defusing the infusion. It can be specified as: \(Example\)

```php
$inf_droptable[1] = DB_SHOUTBOX;
```

When you have Created Tables, so you must also specify the tables to be Dropped at the time of Defusing the infusion. It can be specified as: \(Example\)

```text
$inf_droptable[1] = DB_SHOUTBOX;
```

  
Here, DB\_SHOUTBOX is the constant which holds the Table name in the Database, which is to be droped.  
$inf\_droptable\[1\] represents that it is the 1st table you want to Drop. So, if you want to Drop  
more tables, then you have to create more variables like:  
  
`$inf_droptable[2] = some_table_name;  
$inf_droptable[3] = some_table_name;`  
  
and so on…

**Inserting Rows in Tables**  
  
If you want to insert any Rows into some tables at the time Infusion is being infused, you can  
do it easily. It can be specified as: \(Example\)  
$inf\_insertdbrow\[1\] = DB\_TABLE." \(field1, field2, field3\) VALUES\('some value','some value', 'some value'\)";  
Here, DB\_TABLE is the Table name in Database, in which you want to insert a Row.  
field1, field2 and field3 are the fields of the table, in which you are inserting some values.  
Deleting Rows from Tables  
If you want to delete Rows from tables at the time Infusion is being defused, you can do it as: \(Example\)  
**Code**

```text
$inf_deldbrow[1] = DB_TABLE." WHERE field1='some value'";
```

Here, DB\_TABLE is the Table name in Database, from which you want to delete Rows.  
We have applied a WHERE condition on field1, so that only those rows are deleted, where  
field1 is some value

```text
Adding Admin Page Link & Access Rights of Infusion
```

If you want to insert an Admin page link to the admin panel, you can do it as: \(Example\)  
**Code**

```text
$inf_adminpanel[1] = array(
"title" => "Title of the Admin Page Link",
"image" => "admin_panel_image.gif",
"panel" => "infusion_name_admin.php",
"rights" => "INF"
);
```

  
Here, $inf\_adminpanel\[1\] is an array containing title, image, panel and rights.  
· title is the text tile, which is to be given to the admin page link in admin panel.  
· image is the image file name of the admin page link in admin panel, which exists in the directory administration/images/.  
· panel is the admin page filename of the infusion, say myinfusion\_admin.php.  
· rights contain the short code for admin rights\(e.g SB for ShoutBox\). It must not be more  
than 4 characters.

**Adding Site Link into the site**  


If you want to insert a Site Link in the website, you can do it as: \(Example\)  
**Code**

```text
$inf_sitelink[1] = array(
"title" => "My Infusion",
"url" => "infusions/my_infusion/mypage.php",
"visibility" => "0"
);
```

  
Here, $inf\_sitelink\[1\] is an array containing title, url and visibility of a link, which you would like to add into the website.  
· title is the Title of the link, which is displayed in site.  
· url is the either url to a file from root directory or an external http link.  
· visibility tells, to which the link is to be shown. It could be:  
o 0 - Public  
o 101 - Member  
o 102 - Administrator  
o 103 - Super Administrator

**Adding Multilingual control tables to your infusion**  


If your Infusion have a multilanguage table you will want to populate the System Settings Multilanguage Table toggler with it like  
**Code**

```text
$inf_mlt[1] = array(
"title" => $locale['SB_title'];,
"rights" => "SB"
);
```

  
Here, the $locale\['SB\_title'\] is the Multilanguage Table title for your Multilingual setting and the rights is SB for this, you can call this with ".multilang\_table\("SB"\)."  
For an MySQL query in News simply add**Code**

```text
".(multilang_table("NS") ? "WHERE news_language='".LANGUAGE."' AND" : "WHERE")."
```

  
If the Multilanguage table NS is not enabled the WHERE is triggered instead of language table check.

**Make use of SETTINGS\_INF table whenever required**  


For the Site Settings, we use Settings Table \(DB\_SETTINGS\) for storing/retrieving the settings related to the Core.  
Similarly, For Settings of an infusion, there is a table provided which can be used by an Infusion developer to store/retrieve settings for an infusion.  
The Table is Settings\_INF table \(DB\_SETTINGS\_INF\), which has 3 fields: settings\_name, settings\_value, setting\_inf.  
· settings\_name holds the name of the setting.  
· settings\_value holds the value of the corresponding settings\_name.  
· settings\_inf holds the name of the infusion, for which the settings are stored. \(e.g shoutbox\_panel\)  


**Make use of infusions\_include.php wherever required**  


For helping its developers, PHP-Fusion has provided us with some basic functions which are usually used by some infusions.  
These functions are provided in an include file which is includes/infusions\_include.php.  


**Functions from this file:**  


Quote

> **`filename_exists`**`($dir, $file)`

  
This function returns a unique filename to be made in a directory. It returns a string of the name of the file.

Quote

> **`set_setting`**`($setting_name, $setting_value, $setting_inf)`

  
This function allows you to easily set a value for a setting or insert a setting into the SETTINGS\_INF table used by your infusion. It returns BOOLEAN.  
For example: `set_setting("allow_upload", "yes", "my_infusion");`

**`get_settings`**`($setting_inf)`

  
This function allows you to easily fetch settings of your infusion from the SETTINGS\_INF table in  
form of an array. It returns the array of settings. For example: $inf\_settings = get\_settings\("my\_infusion"\);  
echo $inf\_settings\[‘some\_setting\_name’\]; // It gives you the setting value

> **`send_pm`**`($to, $from, $subject, $message, $smileys = "y")`

  
This function allows you to easily send PM to a User in the site. It returns int. If it returns 0, PM is successfully sent, otherwise failed.  
For example: $msg = send\_pm\(5, 1, "Subject", "Message content", "y"\);

> **`upload_file`**`( $source_file, $target_file = "", $target_folder = DOWNLOADS, $valid_ext =".zip,.rar,.tar,.bz2,.7z", $max_size = "15000", $query = "")`

  
This function allows you to easily upload a file into the site. It returns array of File information.

> **`upload_image`**`($source_image, $target_name = "", $target_folder = IMAGES, $target_width ="1800", $target_height = "1600",$max_size = "150000", $delete_original = false, $thumb1 =true, $thumb2 = true, $thumb1_ratio = 0, $thumb1_folder = IMAGES, $thumb1_suffix ="_t1", $thumb1_width = "100", $thumb1_height = "100",$thumb2_ratio = 0, $thumb2_folder= IMAGES, $thumb2_suffix = "_t2", thumb2_width = "400", $thumb2_height = "300",$query= "")`

  
This function allows you to easily upload an image file into the site. It returns array of image  
File information.

Quote

> **`download_file`**`($file)`

  
This function allows you to start Downloading the file from the site, just like how it outputs Download, when a user downloads a file from the downloads section.

**Comments & Ratings API**  


You can use the Comments & Ratings API for your infusion easily by including two functions:  
· showcomments\(\) - includes/comments\_include.php  
· showratings\(\) - includes/ratings\_include.php  
You must include the corresponding files & call the functions for the API to work.  


**Functions Description**  


Quote

> **`showcomments`**`($ctype, $cdb, $ccol, $cid, $clink)`

  
· $ctype – Comment Type\(A Short code for your infusion, say SB for ShoutBox. Max. of 2 characters\)  
· $cdb – Comment DB\(The Table to which the item corresponds. E.g. article\_id corresponds to DB\_ARTICLES\)  
· $ccol – Comment Column\(The Unique column name to which the item corresponds. E.g. article\_id\)  
· $cid – Comment ID\(The Item ID of the Item\)  
· $clink – The Link, to which it should redirect after posting the comment.

Quote

> **`showratings`**`($rating_type, $rating_item_id, $rating_link)`

  
· $rating\_type – Rating Type\(A Short code for your infusion, say SB for ShoutBox. Max. of 1 character\)  
· $rating\_item\_id – Rating Item ID\(The item ID of the item\)  
· $rating\_link – The Link, to which it should redirect after rating is made.

**Localization Conventions**  
  
The Localization should be done in the familiar manner of PHP-Fusion, which makes it easy for a Developer as well as a Translator, to edit and alter them when required.  
  
**Locales for Infusion related information**  
  
For the infusion related information like $inf\_title & $inf\_description, you may use locale familiar locales like $locale\[‘inf\_title’\] & $locale\[‘inf\_desc’\], where you will replace inf with familiar short code for your Infusion.  
For Example: For ShoutBox infusion, we use the short code as SB. Thus the locales are: $locale\[‘SB\_title’\] & $locale\[‘SB\_desc’\]  
  
**Naming of other Locales**

The Locales should be named on basis of their usage. It makes them familiar and easy for use.  
For Example: If we are using locales, one for user\_name & other for password field, then we  
should use the locales like: $locale\[‘INF\_username’\] & $locale\[‘INF\_password’\]  
Although, there is no harm in using numbered locales like $locale\[‘INF\_001’\] etc but it makes it more familiar.

**Credits**  
The first coding standards document for PHP-Fusion was originally created by PMM, Craig & Ankur in PDF format.

