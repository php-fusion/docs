---
description: Check if user was blacklisted by a member.
---

# user\_blacklisted\(\)

Versions: `9`

user\_blacklisted\( int $user\_id \) : bool

## Parameters <a id="parameters"></a>

$user\_id \(id\) \(Required\) User ID.

## Return Values

\(bool\) True if the user is blacklisted.

## Examples

```php
$user_id = 3;
if (user_blacklisted($user_id)) {
    echo 'User is blacklisted.';
}
```

