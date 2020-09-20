---
description: >-
  Tag a user by simply just posting his name like @Nick and if found, returns a
  tooltip.
---

# fusion\_parse\_user\(\)

Versions: `9`

fusion\_parse\_user\( string $user\_name \[, string $tooltip \] \)

### Parameters <a id="parameters"></a>

$user\_name \(string\) \(Required\) @Nick

$tooltip \(string\) \(Optional\) Additional info \(`$userdata['user_lastvisit']-120 < TIME ? 'Online' : 'Offline'`\)

### Return <a id="return"></a>

\(string\) Tooltip with info

### **Example**

```php
$user_name = '@Nick';
echo fusion_parse_user($user_name);
```

