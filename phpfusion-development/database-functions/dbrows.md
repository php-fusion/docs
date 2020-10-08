---
description: Count the number of rows in a given database query.
---

# dbrows\(\)

Versions: `9`

dbrows\( mixed $result \) : int

## Parameters <a id="parameters"></a>

$result \(string\) \(Required\) The query resource that is being evaluated. This result comes from a call to [dbquery\(\)](dbquery.md).

## Return Values

\(int\) The number of rows in a result set or false on failure.

## Examples

```php
$result = dbquery("SELECT * FROM ".DB_TABLE);
$rows = dbrows($result);
echo $rows;
// The number of rows in the table
```

