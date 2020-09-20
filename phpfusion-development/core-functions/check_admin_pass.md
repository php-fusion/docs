---
description: Check if admin password matches userdata.
---

# check\_admin\_pass\(\)

Versions: `7`, `8`, `9`

check\_admin\_pass\( string $password \)

### Parameters <a id="parameters"></a>

$password \(string\) \(Required\) Password

### Return <a id="return"></a>

\(bool\) This function will return true if the if the $password matches the user's admin password or if the Administrator's cookie or session is set and is valid

### **Example**

```php
if (check_admin_pass('SECRET_PASSWORD')) {
    //
}
```

