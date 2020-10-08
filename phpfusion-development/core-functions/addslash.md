---
description: Add correct number of slashes depending on QUOTES_GPC.
---

# addslash\(\)

Versions: `9`

stripslash\( string $text \) : string

### Parameters <a id="parameters"></a>

$text \(string\) \(Required\) Text to which slashes should be added.

### Return Values

\(string\) String with the correct number of slashes.

### Examples

```php
$text = "Is your name O'reilly?";
echo addslash($text);
// Is your name O\'reilly?
```

