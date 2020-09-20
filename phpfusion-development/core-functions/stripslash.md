---
description: 'Stripslash function, only strip slashes if magic_quotes_gpc is on.'
---

# stripslash\(\)

Versions: `7`, `8`, `9`

stripslash\( string $text \)

### Parameters <a id="parameters"></a>

$text \(string\) \(Required\) The input string

### Return <a id="return"></a>

\(string\) String with backslashes stripped off \(\' becomes ' and so on\). Double backslashes \(\\\) are made into a single backslash \(\\).

### **Example**

```php
$text = 'Is your name O\'reilly?';
echo stripslash($text);
// Is your name O'reilly?
```

