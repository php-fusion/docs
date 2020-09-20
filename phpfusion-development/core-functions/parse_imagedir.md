---
description: Parse and force image/ to own directory.
---

# parse\_imageDir\(\)

Versions: `9`

parse\_imageDir\( string $data \[, string $prefix\_ \] \)

### Parameters <a id="parameters"></a>

$data \(string\) \(Required\) String to parse

$prefix\_ \(string\) \(Optional\) Image folder, default is IMAGES

### Return <a id="return"></a>

\(string\) Parsed string

### **Example**

```php
$data = 'Text <img src="images/img.png" alt="img">';
echo parse_imageDir($data, IMAGES_N);
// Text <img src="infusions/news/images/img.png" alt="img">
```

