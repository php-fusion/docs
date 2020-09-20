---
description: Check if a given theme exists and is valid.
---

# theme\_exists\(\)

Versions: `7`, `8`, `9`

theme\_exists\( string $theme \)

### Parameters <a id="parameters"></a>

$theme \(string\) \(Required\) The theme folder you want to check

### Return <a id="return"></a>

\(bool\) False if the theme does not exist and true if it does.

### **Example**

```php
if (!theme_exists('my_theme')) {
    echo 'my_theme theme does not exist!';
}
```

