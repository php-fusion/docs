---
description: Send a database query.
---

# dbquery\(\)

Versions: `9`

dbquery\( string $query \[, array $parameters \] \) : mixed

## Parameters <a id="parameters"></a>

$query \(string\) \(Required\) A SQL query,

$parameters \(array\) \(Optional\) Parameter identifier. The statement template can contain zero or more named \(:name\) or question mark \(?\) parameter markers for which real values will be substituted when the statement is executed. Default value: \[\]

## Return Values

\(string\|bool\) The result of query or false on error.

## Examples

```php
$result = dbquery("SELECT * FROM ".DB_TABLE." WHERE 1=1");
```

```php
$result = dbquery("SELECT * FROM ".DB_TABLE." WHERE field=:name", [
    ':name' => 'value'
]);
```

