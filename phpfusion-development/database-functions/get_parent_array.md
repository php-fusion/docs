---
description: Get immediate parent array from dbquery_tree_full() result.
---

# get\_parent\_array\(\)

Versions: `9`

get\_parent\_array\( array $data, int $child\_id \) : array

## Parameters <a id="parameters"></a>

$data \(array\) \(Required\) Results from [dbquery\_tree\_full\(\)](dbquery_tree_full.md).

$child\_id \(int\) \(Required\) Child ID.

## Return Values

\(array\)

## Examples

```php
$index = dbquery_tree_full(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
$parent_array = get_parent_array($index, 1);
/*
Array
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
*/
```

