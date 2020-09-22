---
description: 'Strip Input, prevents HTML in unwanted places.'
---

# stripinput\(\)

Versions: `9`

stripinput\( mixed $text \)

### Parameters <a id="parameters"></a>

$text \(mixed\) \(Required\) String or array to be stripped.

### Return Values

\(mixed\) The given string decoded as non HTML text.

### **Examples**

```php
$text = '<a href="www.example.com"><strong>Here is a site</strong></a>';
echo stripinput($text);
// <a href="www.example.com"><strong>Here is a site</strong></a>
```

