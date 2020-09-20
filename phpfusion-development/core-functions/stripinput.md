---
description: 'Strip Input, prevents HTML in unwanted places.'
---

# stripinput\(\)

Versions: `7`, `8`, `9`

stripinput\( mixed $text \)

### Parameters <a id="parameters"></a>

$text \(mixed\) \(Required\) string or array to be stripped

### Return <a id="return"></a>

\(mixed\) $text the given string decoded as non HTML text

### **Example**

```php
echo stripinput('<a href="www.example.com"><strong>Here is a site</strong></a>');
// <a href="www.example.com"><strong>Here is a site</strong></a>
```

