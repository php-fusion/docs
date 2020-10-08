---
description: Fetch user data of the currently logged in user from DB_USERS.
---

# fusion\_get\_userdata\(\)

Versions: `9`

fusion\_get\_userdata\( \[ string $key \] \) : mixed

## Parameters <a id="parameters"></a>

$key \(string\) \(Optional\) The key of one column. Default value: null

## Return Values

\(array\|string\) Associative array of all data or one column by key.

## Examples

```php
$userdata = fusion_get_userdata();
echo $userdata['user_name'];
// admin
```

