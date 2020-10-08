---
description: Get index information from dbquery_tree_full().
---

# tree\_index\(\)

Versions: `9`

tree\_index\( array $data \) : array

## Parameters <a id="parameters"></a>

$data \(array\) \(Required\) Array generated from [dbquery\_tree\_full\(\)](dbquery_tree_full.md).

## Return Values

\(array\)

## Examples

```php
$data = dbquery_tree_full(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
$tree_index = tree_index($data);
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

