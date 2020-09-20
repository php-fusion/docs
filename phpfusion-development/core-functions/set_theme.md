---
description: Set a valid theme.
---

# set\_theme\(\)

Versions: `9`

set\_theme\( string $theme \)

### Parameters <a id="parameters"></a>

$theme \(string\) \(Required\) The theme folder you want to set

### Return <a id="return"></a>

No value is returned

### **Example**

```php
set_theme('my_theme');
```

{% hint style="info" %}
This function can only be called once, in the maincore.php, as it sets CONSTANTS which can not be set again!
{% endhint %}



