---
description: Get hierarchy array with injected child key.
---

# dbtree\(\)

Versions: `9`

dbtree\( string $db, string $id\_col, string $cat\_col \[, string $cat\_value, bool $filter \] \) : array

## Parameters <a id="parameters"></a>

$db \(string\) \(Required\) Table name.

$id\_col \(string\) \(Required\) ID column.

$cat\_col \(string\) \(Required\) Category column.

$cat\_value \(string\) \(Optional\) Category value. Default value: null

$filter \(string\) \(Optional\) Replace conditional structure. Default value: null

## Return Values

\(array\)

## Examples

```php
$data = dbtree(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
/*
Array
(
)
*/
```

