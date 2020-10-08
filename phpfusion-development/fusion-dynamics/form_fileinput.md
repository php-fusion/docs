---
description: Generates a file upload input.
---

# form\_fileinput\(\)

Versions: `9`

form\_fileinput\( string $input\_name \[, string $label, string $input\_value, array $options \] \) : string

The Dynamics Form Fileinput initializes a Jquery based fileinput component wrapper and adds a preset file\_sanitizer file validation and upload handling. The Fileinput is based on [Kartik Bootstrap Fileinput](http://plugins.krajee.com/file-input) plugin for Bootstrap, and is currently one of the more popular fileinput plugin there is available on opensource as it can handle an unprecendented customization configuration layer on a single fileinput widget.

## Parameters <a id="parameters"></a>

$input\_name \(string\) \(Required\) Name of the input, by default it's also used as the ID for the input.

$label \(string\) \(Optional\) Input label. Default value: ''

$input\_value \(string\) \(Optional\) The value to be displayed. Default value: ''

$options \(array\) \(Optional\) Default value: \[\]

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Default</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">input_id</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">$input_name</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">upload_path</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">IMAGES</td>
      <td style="text-align:left">The upload path for the file(s).</td>
    </tr>
    <tr>
      <td style="text-align:left">required</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">Whether this field is required during form submission.</td>
    </tr>
    <tr>
      <td style="text-align:left">safemode</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">Extra security settings such as strict type GD2 checks, and other validation
        during upload.</td>
    </tr>
    <tr>
      <td style="text-align:left">deactivate</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">Disable the input and set it as readonly.</td>
    </tr>
    <tr>
      <td style="text-align:left">preview_off</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">type</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">text</td>
      <td style="text-align:left">Possible value: image, html, text, video, audio, flash, object, file</td>
    </tr>
    <tr>
      <td style="text-align:left">width</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&apos;&apos;</td>
      <td style="text-align:left">Accepts px or % values.</td>
    </tr>
    <tr>
      <td style="text-align:left">label</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">$locale[&apos;browse&apos;]</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">inline</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">true</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">class</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&apos;&apos;</td>
      <td style="text-align:left">The input container wrapper class.</td>
    </tr>
    <tr>
      <td style="text-align:left">tip</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&apos;&apos;</td>
      <td style="text-align:left">Displays a tip by the label.</td>
    </tr>
    <tr>
      <td style="text-align:left">ext_tip</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&apos;&apos;</td>
      <td style="text-align:left">Displays a tip at the bottom of the input.</td>
    </tr>
    <tr>
      <td style="text-align:left">error_text</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">$locale[&apos;error_input_file&apos;]</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">btn_class</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">btn-default</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">icon</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">fa fa-upload</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">jsonurl</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">dropzone</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">valid_ext</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>.jpg,.png,.PNG,.JPG,.JPEG,</p>
        <p>.gif,.GIF,.bmp,.BMP</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">thumbnail</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">Set to true to create primary thumbnail.</td>
    </tr>
    <tr>
      <td style="text-align:left">thumbnail_w</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">300</td>
      <td style="text-align:left">The width of the primary thumbnail.</td>
    </tr>
    <tr>
      <td style="text-align:left">thumbnail_h</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">300</td>
      <td style="text-align:left">The height of the primary thumbnail.</td>
    </tr>
    <tr>
      <td style="text-align:left">thumbnail_folder</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&apos;&apos;</td>
      <td style="text-align:left">The path to the primary thumnail storage.</td>
    </tr>
    <tr>
      <td style="text-align:left">thumbnail_ratio</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">0</td>
      <td style="text-align:left">Keep original ratio or forced square dimension. Possible value: 0, 1</td>
    </tr>
    <tr>
      <td style="text-align:left">thumbnail_suffix</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">_t1</td>
      <td style="text-align:left">Adds a suffix to primary thumbnail filename.</td>
    </tr>
    <tr>
      <td style="text-align:left">thumbnail2</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">Set to true to create secondary thumbnail.</td>
    </tr>
    <tr>
      <td style="text-align:left">thumbnail2_w</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">600</td>
      <td style="text-align:left">The width of the secondary thumbnail.</td>
    </tr>
    <tr>
      <td style="text-align:left">thumbnail2_h</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">400</td>
      <td style="text-align:left">The height of the secondary thumbnail.</td>
    </tr>
    <tr>
      <td style="text-align:left">thumbnail2_suffix</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">_t2</td>
      <td style="text-align:left">Adds a suffix to secondary thumbnail filename.</td>
    </tr>
    <tr>
      <td style="text-align:left">thumbnail2_ratio</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">0</td>
      <td style="text-align:left">Keep original ratio or forced square dimension. Possible value: 0, 1</td>
    </tr>
    <tr>
      <td style="text-align:left">delete_original</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">This is used to delete the uploaded file. It can be used along with thumbnail
        creation where you can set this parameter to true to keep only the thumbnail.</td>
    </tr>
    <tr>
      <td style="text-align:left">max_width</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">1800</td>
      <td style="text-align:left">Defines a maximum alloweable image width. Only takes effect if type is
        set to image.</td>
    </tr>
    <tr>
      <td style="text-align:left">max_height</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">1600</td>
      <td style="text-align:left">Defines a maximum alloweable image height. Only takes effect if type is
        set to image.</td>
    </tr>
    <tr>
      <td style="text-align:left">max_byte</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">15728640</td>
      <td style="text-align:left">Defines a maximum alloweable image size. Only takes effect if type is
        set to image.</td>
    </tr>
    <tr>
      <td style="text-align:left">max_count</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">1</td>
      <td style="text-align:left">Sets a minimum alloweable file selection count per instance. Declare a
        new max_count to 10 to allow user to select 10 files.</td>
    </tr>
    <tr>
      <td style="text-align:left">multiple</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">Whether the current fileinput allows multiple files selection per instance.</td>
    </tr>
    <tr>
      <td style="text-align:left">template</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">classic</td>
      <td style="text-align:left">Customize HTML output of the widget. Possible value: classic, modern,
        thumbnail, avatar, custom</td>
    </tr>
    <tr>
      <td style="text-align:left">media</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">Displays a file media browser selector to allow user to select files within
        the upload_path to pick on.</td>
    </tr>
    <tr>
      <td style="text-align:left">placeholder</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&apos;&apos;</td>
      <td style="text-align:left">A placeholder for the field.</td>
    </tr>
    <tr>
      <td style="text-align:left">form_id</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">&apos;&apos;</td>
      <td style="text-align:left">The current &lt;form&gt; element id that this widget is placed in.</td>
    </tr>
    <tr>
      <td style="text-align:left">hide_upload</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">true</td>
      <td style="text-align:left">Show or hide an upload file button when file has been selected.</td>
    </tr>
    <tr>
      <td style="text-align:left">hide_remove</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">Show or hide an remove file button when file has been selected.</td>
    </tr>
    <tr>
      <td style="text-align:left">krajee_disabled</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">Disables Kartik Bootstrap Jquery plugin and shows a normal browser fileinput
        instead.</td>
    </tr>
    <tr>
      <td style="text-align:left">replace_upload</td>
      <td style="text-align:left">bool</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">Change the upload name to a new unique name upon successful upload.</td>
    </tr>
  </tbody>
</table>

## Return Values

\(string\)

## Examples

```php
echo form_fileinput('upload_field', 'Upload Field');
```

