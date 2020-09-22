---
description: >-
  UF blacklist for SQL - the same as groupaccess() but $field is the user_id
  column.
---

# blacklist\(\)

Versions: `9`

blacklist\( string $field \)

### Parameters <a id="parameters"></a>

$field \(string\) \(Required\) User ID field.

### Return Values

\(string\) It can return an empty condition if the user\_blacklist field is not installed.

### **Examples**

```php
$result = dbquery("SELECT user_id, user_name
    FROM ".DB_USERS."
    WHERE ".blacklist('user_id')."
");
```

