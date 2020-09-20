---
description: Add correct number of slashes depending on QUOTES_GPC.
---

# addslash\(\)

Versions: `9`

stripslash\( string $text \)

### Parameters <a id="parameters"></a>

$text \(string\) \(Required\) Text to which slashes should be added

### Return <a id="return"></a>

\(string\) String with the correct number of slashes

### **Example**

```php
$text = "Is your name O'reilly?";
echo addslash($text);
// Is your name O\'reilly?
```

