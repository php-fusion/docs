---
description: Create a square thumbnail from an already uploaded image.
---

# createsquarethumbnail\(\)

Versions: `9`

createsquarethumbnail\( int $filetype, string $origfile, string $thumbfile, int $new\_size \) : void

## Parameters <a id="parameters"></a>

$filetype \(int\) \(Required\) Possible value: 1 - .gif, 2 -  .jpg, 3 - .png, 4 - .webp

$origfile \(string\) \(Required\) The full path to the original file from which you want to create a thumbnail.

$thumbfile \(string\) \(Required\) The full path to the thumbnail file you want to create.

$new\_size \(int\) \(Required\) Maximum size for thumbnail image.

## Return Values

\(void\)

## Examples

```php
require_once INCLUDES.'photo_functions_include.php';

$origfile = IMAGES.'phpfusion-icon.png';
$thumbfile = IMAGES.'phpfusion-icon_thumb.png';
createsquarethumbnail(3, $origfile, $thumbfile, 100);
```

