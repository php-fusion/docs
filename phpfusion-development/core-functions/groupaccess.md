---
description: Getting the access levels used when asking the database for data.
---

# groupaccess\(\)

Versions: `9`

groupaccess\( string $field \)

### Parameters <a id="parameters"></a>

$field \(string\) \(Required\) MySQL field from which you want to check access

### Return <a id="return"></a>

\(string\) The part of WHERE clause, always returns a condition

### **Example**

```php
$result = dbquery("SELECT item, access
    FROM ".DB_TABLE."
    WHERE ".groupaccess('access')."
    ORDER BY item DESC
");
```

