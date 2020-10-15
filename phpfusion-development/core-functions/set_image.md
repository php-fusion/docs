---
description: Set a path of an image.
---

# set\_image\(\)

Versions: `9`

set\_image\( string $name, string $path \) : void

## Parameters <a id="parameters"></a>

$name \(string\) \(Required\) The name of an already defined image whose location you want to change, or your own image.

$path \(string\) \(Required\) The path to the image you are setting.

## Return Values

No value is returned.

## Examples

```php
// Change the path of the defined image
set_image('noavatar', 'new/path/no-avatar.jpg');

// Set own image
set_image('new_image', 'path/image.jpg');
```

