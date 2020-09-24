---
description: Check if admin password matches userdata.
---

# check\_admin\_pass\(\)

Versions: `9`

check\_admin\_pass\( string $password \) : bool

### Parameters <a id="parameters"></a>

$password \(string\) \(Required\) Password.

### Return Values

\(bool\) This function will return true if the if the password matches the user's admin password or if the admin's cookie or session is set and is valid.

### **Examples**

```php
if (check_admin_pass('SECRET_PASSWORD')) {
    //
}
```

