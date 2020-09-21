---
description: Add correct amount of spaces and tabs inside code.
---

# formatcode\(\)

Versions: `9`

formatcode\( string $text \)

### Parameters <a id="parameters"></a>

$text \(string\) \(Required\) The text you want to format

### Return <a id="return"></a>

\(string\) Formatted code

### **Example**

```php
$text = '   Indent goes here.';
echo formatcode($text);
// &nbsp; &nbsp;Indent goes here.
```

