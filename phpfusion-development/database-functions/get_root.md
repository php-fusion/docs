---
description: Get tree root ID of a child from dbquery_tree() result.
---

# get\_root\(\)

Versions: `9`

get\_root\( array $index, int $child\_id \) : int

## Parameters <a id="parameters"></a>

$index \(array\) \(Required\) Results from [dbquery\_tree\(\)](dbquery_tree.md).

$child\_id \(int\) \(Required\) Child ID.

## Return Values

\(int\)

## Examples

```php
$index = dbquery_tree(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
$root = get_root($index, 1);
// 1
```

