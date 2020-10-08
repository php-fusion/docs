---
description: >-
  Check if user is assigned to the specified user group and has the required
  user level.
---

# checkusergroup\(\)

Versions: `9`

checkusergroup\( int $group, int $user\_level, string $user\_groups \) : bool

### Parameters <a id="parameters"></a>

$group \(int\) \(Required\) The group number you want to check for the user.

$user\_level \(int\) \(Required\) User level.

$user\_groups \(string\) \(Required\) Assigned groups to the user.

### Return Values

\(bool\) True if the user has access.

### Examples

```php
$page_access = USER_LEVEL_MEMBER;
$userdata = fusion_get_userdata();
if (checkusergroup($page_access, $userdata['user_level'], $userdata['user_groups'])) {
    echo 'You have access to this section.';
}
```

