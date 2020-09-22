---
description: 'Stripslash function, only strip slashes if magic_quotes_gpc is on.'
---

# stripslash\(\)

Versions: `9`

stripslash\( string $text \)

### Parameters <a id="parameters"></a>

$text \(string\) \(Required\) The input string.

### Return Values

\(string\) String with backslashes stripped off \(\' becomes ' and so on\), double backslashes \(\\\) are made into a single backslash \(\\).

### **Examples**

```php
$text = 'Is your name O\'reilly?';
echo stripslash($text);
// Is your name O'reilly?
```

