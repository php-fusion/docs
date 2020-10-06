---
description: Checks the panel status for given side.
---

# check\_panel\_status\(\)

Versions: `9`

check\_panel\_status\( string $side \) : bool

### Parameters <a id="parameters"></a>

$side \(string\) \(Required\) Possible value: left, right, upper, aupper, lower, blower, user1, user2, user3, user4

### Return Values

\(bool\)

### **Examples**

```php
if (check_panel_status('left')) {
    //
}
```

