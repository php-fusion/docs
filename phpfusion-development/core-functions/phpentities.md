---
description: Converts all applicable characters to HTML entities.
---

# phpentities\(\)

Versions: `9`

phpentities\( string $text \) : string

### Parameters <a id="parameters"></a>

$text \(string\) \(Required\) The input string.

### Return Values

\(string\) Encoded string.

### **Examples**

```php
$text = "A 'quote' is <b>bold</b>";
echo phpentities($text);
// A &#039;quote&#039; is &lt;b&gt;bold&lt;/b&gt;
```

