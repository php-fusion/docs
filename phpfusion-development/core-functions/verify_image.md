---
description: Scan image files for malicious code.
---

# verify\_image\(\)

Versions: `9`

verify\_image\( string $file \) : bool

## Parameters <a id="parameters"></a>

$file \(string\) \(Required\) Path to image.

## Return Values

\(bool\) True or false, depending on whether the image is safe or not.

## Examples

```php
$file = IMAGES.'phpfusion-icon.png';
if (verify_image($file)) {
    echo 'The image is safe.';
} else {
    echo 'The image is not safe.';
}
// The image is safe.
```

