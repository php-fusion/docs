---
description: Get information about a specific image.
---

# exif\(\)

Versions: `9`

exif\( string $imagePath \) : mixed

## Parameters <a id="parameters"></a>

$imagePath \(string\) \(Required\) Path to the image.

## Return Values

\(array\|false\) False, if the image does not exist.

## Examples

```php
require_once INCLUDES.'photo_functions_include.php';

$imagePath = IMAGES.'php-fusion-logo.png';
exif($imagePath);
/*
Array
(
    [width] => 295
    [height] => 99
    [mime] => image/png
    [channels] => 
    [bits] => 8
    [make] => No information available
    [model] => No information available
    [exposure] => No information available
    [aperture] => No information available
    [date] => No information available
    [iso] => No information available
)
*/
```

