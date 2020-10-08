---
description: Get parent IDs from dbquery_tree() result.
---

# get\_all\_parent\(\)

Versions: `9`

get\_all\_parent\( array $index, int $child\_id \[, array $list \] \) : mixed

## Parameters <a id="parameters"></a>

$index \(array\) \(Required\) Results from [dbquery\_tree\(\)](dbquery_tree.md).

$child\_id \(int\) \(Required\) Child ID.

$list \(array\) \(Optional\) Default value: \[\]

## Return Values

\(array\|int\)

## Examples

```php
$index = dbquery_tree(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
$parent = get_all_parent($index, 1);
// 0
```

