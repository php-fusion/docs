---
description: UF blacklist for SQL.
---

# blacklist\(\)

Versions: `9`

blacklist\( string $field \) : string

### Parameters <a id="parameters"></a>

$field \(string\) \(Required\) User ID field.

### Return Values

\(string\) It can return an empty condition if the user\_blacklist field is not installed.

### Examples

```php
$result = dbquery("SELECT user_id, user_name
    FROM ".DB_USERS."
    WHERE ".blacklist('user_id')."
");
```

