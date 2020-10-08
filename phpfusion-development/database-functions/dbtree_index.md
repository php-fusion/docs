---
description: Lighter version of dbtree() with only id and child key.
---

# dbtree\_index\(\)

Versions: `9`

dbtree\( string $db, string $id\_col, string $cat\_col \[, string $cat\_value \] \) : array

### Parameters <a id="parameters"></a>

$db \(string\) \(Required\) Table name.

$id\_col \(string\) \(Required\) ID column.

$cat\_col \(string\) \(Required\) Category column.

$cat\_value \(string\) \(Optional\) Category value. Default value: null

### Return Values

\(array\)

### Examples

```php
$data = dbtree_index(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
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

