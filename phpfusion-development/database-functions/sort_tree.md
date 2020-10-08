---
description: To sort key on dbtree_index results.
---

# sort\_tree\(\)

Versions: `9`

sort\_tree\( array $result, string $key \) : array

## Parameters <a id="parameters"></a>

$result \(array\) \(Required\) [dbtree\_index\(\)](dbtree_index.md) result.

$key \(string\) \(Required\) Key.

## Return Values

\(array\)

## Examples

```php
$result = dbtree_index(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
$data = sort_tree($result, 'news_cat_id');
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

