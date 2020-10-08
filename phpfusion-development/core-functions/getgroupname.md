---
description: Get the name of the access level or user group.
---

# getgroupname\(\)

Versions: `9`

getgroupname\( int $group\_id \[, bool $return\_desc, bool $return\_icon \] \) : mixed

### Parameters <a id="parameters"></a>

$group\_id \(int\) \(Required\) The ID of the group or access level to which you want to get a name.

$return\_desc \(bool\) \(Optional\) If true, description will be returned instead of name. Default value: false

$return\_icon \(bool\) \(Optional\) If true, icon will be returned next to name. Default value: false

### Return Values

\(string\|null\) The name or icon or description of the given group, null if does not exist.

### Examples

```php
echo getgroupname(1, false, true);
// <i class='fa fa-user'></i> Group Name
```

