---
description: Show image thumbnail.
---

# thumbnail\(\)

Versions: `9`

thumbnail\( string $src, string $size \[, bool $url, bool $colorbox, bool $responsive, string $class \] \) : string

## Parameters <a id="parameters"></a>

$src \(string\) \(Required\) The path to image.

$size \(string\) \(Required\) Image size.

$url \(bool\) \(Optional\) Make image clickable. Default value: false

$colorbox \(bool\) \(Optional\) Allow [colorbox\(\)](colorbox.md). Default value: false

$responsive \(bool\) \(Optional\) Add img-responsive class. Default value: true

$class \(string\) \(Optional\) CSS class. Default value: ''

## Return Values

\(string\)

## Examples

```php
echo thumbnail(IMAGES.'php-fusion-logo.png', '100px');
```

