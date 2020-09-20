---
description: Set a valid theme.
---

# set\_theme\(\)

Versions: `7`, `8`, `9`

set\_theme\( string $theme \)

### Parameters <a id="parameters"></a>

$theme \(string\) \(Required\) The theme folder you want to set

### Return <a id="return"></a>

\(true\)

### **Example**

```php
set_theme('Magazine');
```

### Notes

This function can only be called once, in the maincore.php, as it sets CONSTANTS which can not be set again!

