---
description: Pure trim function.
---

# trim\_text\(\)

Versions: `9`

trim\_text\( string $text \[, int $length \] \)

### Parameters <a id="parameters"></a>

$text \(string\) \(Required\) String to trim

$length \(int\) \(Optional\) The number of characters

### Return <a id="return"></a>

\(string\) Trimmed text

### **Example**

```php
$text = 'The big brown fox jumped over the lazy dog';
echo trim_text($text, 10);
// The big brown...
```

