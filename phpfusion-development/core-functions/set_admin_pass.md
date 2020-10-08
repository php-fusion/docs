---
description: Set password of the currently logged in an administrator.
---

# set\_admin\_pass\(\)

Versions: `9`

set\_admin\_pass\( string $password \) : bool

The function will set the `$_COOKIE[COOKIE_PREFIX.'admin']` if the submitted admin password matches the users admin password in `$userdata['user_admin_password']`.

### Parameters <a id="parameters"></a>

$password \(string\) \(Required\) Any password.

### Return Values

\(bool\) True if a password is set.

### Examples

```php
set_admin_pass('SECRET_PASSWORD');
```

