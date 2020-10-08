---
description: Determine whether column exists in a table.
---

# column\_exists\(\)

Versions: `9`

column\_exists\( string $table, string $column \[, bool $add\_prefix \] \) : bool

## Parameters <a id="parameters"></a>

$table \(string\) \(Required\) Table name.

$column \(string\) \(Required\) Column name.

$add\_prefix \(bool\) \(Optional\) Delimiter. Default value: true

## Return Values

\(bool\)

## Examples

```php
if (column_exists(DB_USERS, 'user_name')) {
    //
}
```

