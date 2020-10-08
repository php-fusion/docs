---
description: Get current depth from dbquery_tree() result.
---

# get\_depth\(\)

Versions: `9`

get\_depth\( array $index, int $child\_id \[, int $depth \] \) : array

## Parameters <a id="parameters"></a>

$index \(array\) \(Required\) Results from [dbquery\_tree\(\)](dbquery_tree.md).

$child\_id \(int\) \(Required\) Child ID.

$depth \(int\) \(Optional\) Default value: null

## Return Values

\(array\)

## Examples

```php
$index = dbquery_tree(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
$depth = get_depth($index, 1);
// 1
```

