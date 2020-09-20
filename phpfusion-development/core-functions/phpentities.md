---
description: Converts all applicable characters to HTML entities.
---

# phpentities\(\)

Versions: `7`, `8`, `9`

phpentities\( string $text \)

### Parameters <a id="parameters"></a>

$text \(string\) \(Required\) The input string

### Return <a id="return"></a>

\(string\) Encoded string

### **Example**

```php
$text = "A 'quote' is <b>bold</b>";
echo phpentities($text);
// A &#039;quote&#039; is &lt;b&gt;bold&lt;/b&gt;
```

