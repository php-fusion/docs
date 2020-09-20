---
description: Strips a given filename from any unwanted characters and symbols.
---

# stripfilename\(\)

Versions: `7`, `8`, `9`

stripfilename\( string $filename \)

### Parameters <a id="parameters"></a>

$filename \(string\) \(Required\) Filename you want to strip. Remember to remove the file extension before parsing it through this function.

### Return <a id="return"></a>

\(string\) The filename stripped and ready for use

### **Example**

```php
$filename = 'I am-Ã… test file!!!??.jpg';

// File name without file extension
$filename = preg_replace('/\\.[^.\\s]{3,4}$/', '', $filename);

echo stripfilename($filename);

// i_am-_test_file
```

