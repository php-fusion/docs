---
description: 'Strip Input, prevents HTML in unwanted places.'
---

# stripinput\(\)

Versions: `9`

stripinput\( mixed $text \)

### Parameters <a id="parameters"></a>

$text \(mixed\) \(Required\) String or array to be stripped

### Return <a id="return"></a>

\(mixed\) The given string decoded as non HTML text

### **Example**

```php
$text = '<a href="www.example.com"><strong>Here is a site</strong></a>';
echo stripinput($text);
// <a href="www.example.com"><strong>Here is a site</strong></a>
```

