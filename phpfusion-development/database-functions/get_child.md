---
description: Get child IDs from dbquery_tree() result.
---

# get\_child\(\)

Versions: `9`

get\_child\( array $index, int $parent\_id \[, array $children \] \) : array

### Parameters <a id="parameters"></a>

$index \(array\) \(Required\) Results from [dbquery\_tree\(\)](dbquery_tree.md).

$parent\_id \(int\) \(Required\) Parent ID.

$children \(array\) \(Optional\) Default value: \[\]

### Return Values

\(array\)

### Examples

```php
$index = dbquery_tree(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
$child = get_child($index, 1);
/*
Array
(
)
*/
```

