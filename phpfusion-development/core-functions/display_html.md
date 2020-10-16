---
description: Display set of buttons.
---

# display\_html\(\)

Versions: `9`

display\_html\( string $formname, string $textarea \[, bool $html, bool $colors, bool $images, string $folder \] \) : string

## Parameters <a id="parameters"></a>

$formname \(string\) \(Required\) The name of the form you are using the HTML buttons for.

$textarea \(string\) \(Required\) The name of the textarea which html will be inserted to.

$html \(bool\) \(Optional\) Setting this to true will display the HTML buttons, set this to false to prevent them from displaying. Default value: true

$colors \(bool\) \(Optional\) Setting this to true will display the HTML colors, set this to false to prevent them from displaying. Default value: true

$images \(bool\) \(Optional\) Setting this to true will display the select field with images, set this to false to prevent them from displaying. Default value: true

$folder \(string\) \(Optional\) If you have $images set to true, use this to define what image folder you want to get images from. Default value: ''

## Return Values

\(string\)

## Examples

```php
echo openform('testform', 'post');
echo form_textarea('test_textarea');
echo display_html('testform', 'test_textarea');
echo closeform();
```

