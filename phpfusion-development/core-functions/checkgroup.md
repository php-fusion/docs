---
description: Check if user is assigned to the specified user group.
---

# checkgroup\(\)

Versions: `9`

checkgroup\( int $group \)

### Parameters <a id="parameters"></a>

$group \(int\) \(Required\) The group number you want to check for the user

### Return <a id="return"></a>

\(bool\) True if the user is in the group

### **Example**

```php
$group = -101;
if (checkgroup($group)) {
    echo 'You are a member of the '.getgroupname($group).' group.';
}
// You are a member of the Member group.
```

