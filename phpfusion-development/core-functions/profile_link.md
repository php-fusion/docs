---
description: User profile link.
---

# profile\_link\(\)

Versions: `9`

profile\_link\( int $user\_id, string $user\_name, int $user\_status \[, string $class, bool $display\_link \] \) : string

### Parameters <a id="parameters"></a>

$user\_id \(int\) \(Required\)

$user\_name \(string\) \(Required\)

$user\_status \(int\) \(Required\)

$class \(string\) \(Optional\) CSS class for the profile link. Default value: profile-link

$display\_link \(bool\) \(Optional\) Allow clicking on the name, otherwise display only the name. Default value: true

### Return Values

\(string\) Link to the user's account along with the user name correctly depending on the user's status.

### **Examples**

```php
$userdata = fusion_get_userdata();
echo profile_link($userdata['user_id'], $userdata['user_name'], $userdata['user_status']);
// <a href='profile.php?lookup=1' class='profile-link'>admin</a>
```

