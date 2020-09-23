---
description: Fetch user PM settings.
---

# user\_pm\_settings\(\)

Versions: `9`

user\_pm\_settings\( int $user\_id \[, string $key \] \)

### Parameters <a id="parameters"></a>

$user\_id \(int\) \(Required\) User ID.

$key \(string\) \(Optional\) The key of one column. Default value: null

### Return Values

\(array\|string\) Associative array of all data or one column by key.

### **Examples**

```php
$pm_settings = user_pm_settings(1);
echo $pm_settings['user_pm_email_notify'];
// 1
```

