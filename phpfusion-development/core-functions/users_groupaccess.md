---
description: Check if user has access to the group.
---

# users\_groupaccess\(\)

Versions: `9`

users\_groupaccess\( int $group\_id \) : bool

## Parameters <a id="parameters"></a>

$group\_id \(int\) \(Required\) The ID of the group.

## Return Values

\(bool\) True if the user has access.

## Examples

```php
$id = 1;
if (users_groupaccess($id)) {
    echo 'User has access to '.getgroupname($id);
}
```

