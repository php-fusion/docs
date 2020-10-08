---
description: Get the next auto_increment id of a table.
---

# dbnextid\(\)

Versions: `9`

dbnextid\( string $table \) : int

## Parameters <a id="parameters"></a>

$table \(string\) \(Required\) Database table.

## Return Values

\(int\)

## Examples

```php
echo dbnextid(DB_TABLE);
```

