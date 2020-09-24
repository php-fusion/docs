---
description: Check if a given theme exists and is valid.
---

# theme\_exists\(\)

Versions: `9`

theme\_exists\( string $theme \) : bool

### Parameters <a id="parameters"></a>

$theme \(string\) \(Required\) The theme folder you want to check.

### Return Values

\(bool\) False if the theme does not exist and true if it does.

### **Examples**

```php
if (!theme_exists('my_theme')) {
    echo 'my_theme theme does not exist!';
}
```

