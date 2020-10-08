---
description: Log user actions.
---

# save\_user\_log\(\)

Versions: `9`

save\_user\_log\( int $user\_id, string $column\_name, string $new\_value, string $old\_value \) : void

### Parameters <a id="parameters"></a>

$user\_id \(int\) \(Required\) User ID.

$column\_name \(string\) \(Required\) Affected column.

$new\_value \(string\) \(Required\) New value.

$old\_value \(string\) \(Required\) Old value.

### Return Values

No value is returned.

### Examples

```php
$userdata = fusion_get_userdata();
save_user_log($userdata['user_id'], 'user_name', 'NewName', $userdata['user_name']);
```

