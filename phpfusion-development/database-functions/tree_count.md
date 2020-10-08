---
description: Count result from dbquery_tree().
---

# tree\_count\(\)

Versions: `9`

tree\_count\( array $data \[, string $column\_name, string $value\_to\_match \] \) : int

## Parameters <a id="parameters"></a>

$data \(array\) \(Required\) Results from [dbquery\_tree\(\)](dbquery_tree.md).

$column\_name \(string\) \(Optional\) Default value: null

$value\_to\_match \(string\) \(Optional\) Default value: null

## Return Values

\(int\)

## Examples

```php
$data = dbquery_tree(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
$tree_count = tree_count($data);
// 1
```

