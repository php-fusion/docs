---
description: Prevent strings from growing to long and breaking the layout.
---

# trimlink\(\)

Versions: `9`

trimlink\( string $text, int $length \)

### Parameters <a id="parameters"></a>

$text \(string\) \(Required\) String to trim

$length \(int\) \(Required\) Max length of the string

### Return <a id="return"></a>

\(string\) String trimmed to the given length

### **Example**

```php
$text = 'The big brown fox jumped over the lazy dog';
echo trimlink($text, 10);
// The big...
```

