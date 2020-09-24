---
description: Parse and force image/ to own directory.
---

# parse\_imageDir\(\)

Versions: `9`

parse\_imageDir\( string $data \[, string $prefix\_ \] \) : string

### Parameters <a id="parameters"></a>

$data \(string\) \(Required\) String to parse.

$prefix\_ \(string\) \(Optional\) Image folder. Default value: IMAGES

### Return Values

\(string\) Parsed string.

### **Examples**

```php
$data = 'Text <img src="images/img.png" alt="img">';
echo parse_imageDir($data, IMAGES_N);
// Text <img src="infusions/news/images/img.png" alt="img">
```

