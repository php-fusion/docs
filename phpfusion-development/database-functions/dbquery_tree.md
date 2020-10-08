---
description: Hierarchy ID to category output.
---

# dbquery\_tree\(\)

Versions: `9`

dbquery\_tree\( string $db, string $id\_col, string $cat\_col \[, bool $filter, string $query\_replace \] \) : array

## Parameters <a id="parameters"></a>

$db \(string\) \(Required\) Table name.

$id\_col \(string\) \(Required\) ID column.

$cat\_col \(string\) \(Required\) Category column.

$filter \(string\) \(Optional\) Replace conditional structure. Default value: null

$query\_replace \(string\) \(Optional\) Replace the entire query structure. Default value: null

## Return Values

\(array\) Returns cat-id relationships.

## Examples

```php
$data = dbquery_tree(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
/*
Array
(
    [0] => Array
        (
            [0] => 1
            [1] => 2
            [2] => 3
            ....
        )
)
*/
```

