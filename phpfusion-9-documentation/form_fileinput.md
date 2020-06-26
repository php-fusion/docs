---
description: form_fileinput - ui for fileinput
---

# form\_fileinput

`(Version 7)` `(Version 8)` `(Version 9)`

## Description

form\_fileinput`( string $input_name, string $label, string|array $input_value, array $options) : string`

The Dynamics Form Fileinput initializes a Jquery based fileinput component wrapper and adds a preset file\_sanitizer file validation and upload handling. The Fileinput is based on [Kartik Bootstrap Fileinput](http://plugins.krajee.com/file-input) plugin for Bootstrap, and is currently one of the more popular fileinput plugin there is available on opensource as it can handle an unprecendented customization configuration layer on a single fileinput widget. On top of that, we also have extended a Cropbox option based on [Foliotek's Croppie plugin](https://foliotek.github.io/Croppie/) to work in symbiosis to complement image adjustments and file selection experience for the user.

The options parameters can be passed for customizing the widget's apperance, intended upload paths, primary thumbnail creation, secondary thumbnail creation, jquery event handler, caption and button apperances among others features as may be extended by the Kartik plugin.

Returns a string of html codes, adds defender session and adds jquery codes for the widget initiliazation.

```text
<?php
$options = array(
    "upload_path" => IMAGES,
    "replace_upload" => TRUE,
);
echo openform("uploadFrm", "post", FORM_REQUEST, array("enctype"=>TRUE);
echo form_fileinput('my_upload', "Upload Document or Photos", $input_value, $options);
...
echo closeform();
?>
```

### Parameters

The `$options` can be configured with the essentials. Most of these are optional, except `upload_path` key which is required to handle file upload.

| Key | Description | Default Values |
| :--- | :--- | :--- |
| input\_id | DOM ID | $input\_name |
| upload\_path | The upload path for the file\(s\) | IMAGES |
| required | Whether this field is required during form submission | FALSE |
| safemode | Extra security settings such as strict type GD2 checks, and other validation during upload | FALSE |
| deactivate | Disable the input and set it as readonly | FALSE |
| replace\_upload | Change the upload name to a new unique name upon successful upload | - |
| preview\_off |  |  |
| type | Defines the media type acceptable | image \(image, object, audio, video\) |
| width |  | - \(accepts px or % values\) |
| inner\_width |  | 100% \(accepts px or % values\) |
| label |  |  |
| inline | Displays the field inline or otherwise | FALSE |
| class | The input container wrapper class | - |
| tip | Displays a tip by the label | - |
| ext\_tip | Displays a tip by the bottom of the input widget | - |
| error\_text |  | $locale\["error\_input\_file"\] |
| btn\_class |  | btn-default |
| icon |  | fa fa-upload m-r-5 |
| jsonurl |  | \(boolean\) FALSE |
| async |  | \(string\) false |
| dropzone |  | \(boolean\)false |
| valid\_ext |  | JPG,.JPEG,.BMP,.GIF,.TIFF,.PNG,.WEBP,.TIF,.TIFF,.SVG |
| thumbnail | Set to true to create primary thumbnail | \(boolean\) false |
| thumbnail\_w | The width of the primary thumbnail | \(int\) 300 |
| thumbnail\_h | The height of the primary thumbnail | \(int\) 300 |
| thumbnail\_folder | The path to the primary thumnail storage. | "" |
| thumbnail\_ratio | Keep original ratio or forced square dimension. | 0 |
| thumbnail\_suffix | Adds a suffix to primary thumbnail filename. | \_t1 |
| thumbnail2 | Set to true to create secondary thumbnail | \(boolean\) false |
| thumbnail2\_w | The width of the secondary thumbnail | \(int\) 600 |
| thumbnail2\_h | The height of the secondary thumbnail | \(int\) 400 |
| thumbnail2\_ratio | Keep original ratio or forced square dimension. | 0 |
| thumbnail2\_suffix | Adds a suffix to secondary thumbnail filename. | \_t2 |
| delete\_original | This is used to delete the uploaded file. It can be used along with thumbnail creation where you can set this parameter to true to keep only the thumbnail. | \(boolean\)FALSE |
| button\_text | Customize button text for the select file button | - |
| default\_preview | Define a default image as placeholder | IMAGES."no\_photo.png" |
| max\_width | Defines a maximum alloweable image width. Only takes effect if type is set to 'image'. Values should be integer representing actual pixels length | 3840 |
| max\_height | Defines a maximum alloweable image height. Only takes effect if type is set to 'image'. Values should be integer representing actual pixels length | 2160 |
| max\_byte | Defines a maximum alloweable image size. Only takes effect if type is set to 'image'. Values should be integer representing actual byte size | 16588800 |
| min\_width | Defines a minimum alloweable image width. Only takes effect if type is set to 'image'. Values should be integer representing actual pixels length | 100 |
| min\_height | Defines a minimum alloweable image height. Only takes effect if type is set to 'image'. Values should be integer representing actual pixels length | 100 |
| multiple | Whether the current fileinput allows multiple files selection per instance. | FALSE |
| max\_count | Sets a minimum alloweable file selection count per instance. Declare a new max\_count to 10 to allow user to select 10 files. | 1 |
| template | Customize HTML output of the widget. There are several premade examples available. | classic \(classic, modern, thumbnail, avatar, custom\) |
| placeholder | A placeholder for the field caption | - |
| media | Displays a file media browser selector to allow user to select files within the upload\_path to pick on | FALSE |
| form\_id | The current `<form>` element id that this widget is placed in | - |
| hide\_upload | Show or hide an upload file button when file has been selected | TRUE |
| hide\_remove | Show or hide an remove file button when file has been selected | FALSE |
| krajee\_disabled | Disables Kartik Bootstrap Jquery plugin and shows a normal browser fileinput instead | FALSE |
| js\_error\_handler | Custom Jquery error event handling for Kartik Bootstrap Jquery plugin | - |
| js\_success\_handler | Custom Jquery success event handling for Kartik Bootstrap Jquery plugin | - |
| js\_change\_handler | Custom Jquery change event handling for Kartik Bootstrap Jquery plugin | - |
| croppie | To trigger a crop box upon image file selection | FALSE |
| croppie\_resize | Crop box allows resizing selected image | FALSE |
| croppie\_zoom | Crop box allows zooming the selected image | FALSE |
| croppie\_zoomer | Crop box displays a zoom slider UI | FALSE |
| croppie\_viewport\_width | The width of the cropbox | 200 |
| debug | Prints a debug to show the Jquery code that will be parsed. | FALSE |

### Return Values

Returns the fileinput widget

### Advanced Examples

#### Jquery Ajax Upload Examples

