---
description: Sort tree an associative array.
---

# sorter\(\)

Versions: `9`

sorter\( array $array, string $key \[, string $sort \] \) : array

### Parameters <a id="parameters"></a>

$array \(array\) \(Required\)

$key \(string\) \(Required\) Key.

$sort \(string\) \(Optional\) Default value: ASC

### Return Values

\(array\)

### Examples

```php
$array = dbquery_tree_full(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
$data = sorter($array, 'news_cat_id');
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

