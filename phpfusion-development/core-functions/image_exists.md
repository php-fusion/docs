---
description: Find another available image name based on the image in the folder.
---

# image\_exists\(\)

Versions: `9`

image\_exists\( string $dir, string $image \) : string

## Parameters <a id="parameters"></a>

$dir \(string\) \(Required\) The directory to check for the image, remember a / at the end of the directory path.

$image \(string\) \(Required\) The image inside the directory you want to check for.

## Return Values

\(string\)

## Examples

```php
require_once INCLUDES.'photo_functions_include.php';

echo image_exists(IMAGES, 'php-fusion-icon.png');
// php-fusion-icon_1.png
```

