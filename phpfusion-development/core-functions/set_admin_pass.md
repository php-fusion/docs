---
description: Set password of the currently logged in administrator.
---

# set\_admin\_pass\(\)

Versions: `7`, `8`, `9`

set\_admin\_pass\( string $password \)

The function will set the `$_COOKIE[COOKIE_PREFIX.'admin']` if the submitted admin password matches the users admin password in `$userdata['user_admin_password']`.

### Parameters <a id="parameters"></a>

$password \(string\) \(Required\) Any password

### Return <a id="return"></a>

\(bool\)

### **Example**

```php
set_admin_pass('SECRET_PASSWORD');
```

