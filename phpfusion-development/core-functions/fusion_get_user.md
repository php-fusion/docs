---
description: Get the data of any user by ID.
---

# fusion\_get\_user\(\)

Versions: `9`

fusion\_get\_user\( int $user\_id \[, string $key \] \) : mixed

### Parameters <a id="parameters"></a>

$user\_id \(int\) \(Required\) User ID.

$key \(string\) \(Optional\) The key of one column. Default value: null

### Return Values

\(array\|string\) Associative array of all data or one column by key.

### Examples

```php
$userdata = fusion_get_user(1);
echo $userdata['user_name'];
// admin
```

