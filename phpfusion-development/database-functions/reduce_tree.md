---
description: >-
  Reduce the results of a hierarchy tree array to a non multidimensional single
  output value while preserving keys.
---

# reduce\_tree\(\)

Versions: `9`

reduce\_tree\( array $result, string $id\_col \) : array

## Parameters <a id="parameters"></a>

$result \(array\) \(Required\) Results from [dbquery\_tree\_full\(\)](dbquery_tree_full.md) or [dbquery\_tree\(\)](dbquery_tree.md).

$id\_col \(string\) \(Required\) ID column.

## Return Values

\(array\)

## Examples

```php
$result = dbquery_tree_full(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
$tree = reduce_tree($result, 'news_cat_id');
/*
Array
(
    [1] => Array
        (
            [news_cat_id] => 1
            [news_cat_parent] => 0
            [news_cat_name] => Bugs
            [news_cat_image] => bugs.svg
            [news_cat_visibility] => 0
            [news_cat_draft] => 0
            [news_cat_sticky] => 0
            [news_cat_language] => English
        )
    ....
)
*/
```

