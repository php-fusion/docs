---
description: Hierarchy full data output.
---

# dbquery\_tree\_full\(\)

Versions: `9`

dbquery\_tree\_full\( string $db, string $id\_col, string $cat\_col \[, bool $filter, string $query\_replace \] \) : array

### Parameters <a id="parameters"></a>

$db \(string\) \(Required\) Table name.

$id\_col \(string\) \(Required\) ID column.

$cat\_col \(string\) \(Required\) Category column.

$filter \(string\) \(Optional\) Replace conditional structure. Default value: null

$query\_replace \(string\) \(Optional\) Replace the entire query structure. Default value: null

### Return Values

\(array\) Returns cat-id relationships with full data.

### **Examples**

```php
$data = dbquery_tree_full(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
/*
Array
(
    [0] => Array
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
)
*/
```

