---
description: Count the number of rows in a table.
---

# dbcount\(\)

Versions: `9`

dbcount\( string $field, string $table \[, string $conditions, array $parameters \] \) : int

### Parameters <a id="parameters"></a>

$field \(string\) \(Required\) The field that you want to count in the database.

$table \(string\) \(Required\) The table you want to count from.

$conditions \(string\) \(Optional\) The conditions you want to the results to match. Default value: ''

$parameters \(array\) \(Optional\) Parameter identifier. The statement template can contain zero or more named \(:name\) or question mark \(?\) parameter markers for which real values will be substituted when the statement is executed. Default value: \[\]

### Return Values

\(int\) The number of rows in the table.

### Examples

```php
echo dbcount("(field1)", DB_TABLE, "field1='this'");
```

