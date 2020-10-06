---
description: 'Hierarchy Page Breadcrumbs, generates breadcrumbs on all your category needs.'
---

# make\_page\_breadcrumbs\(\)

Versions: `9`

make\_page\_breadcrumbs\( array $tree\_index, array $tree\_full, string $id\_col, string $title\_col \[, string $getname, string $key \] \) : void

### Parameters <a id="parameters"></a>

$tree\_index \(array\) \(Required\) tree\_index\(dbquery\_tree\_full\(DB\_NEWS\_CATS, 'news\_cat\_id', 'news\_cat\_parent'\)\).

$tree\_full \(array\) \(Required\) dbquery\_tree\_full\(DB\_NEWS\_CATS, 'news\_cat\_id', 'news\_cat\_parent'\).

$id\_col \(string\) \(Required\) news\_cat\_id.

$title\_col \(string\) \(Required\) news\_cat\_name.

$getname \(string\) \(Optional\) The name of the $\_GET parameter. Default value: rownav

$key \(string\) \(Optional\) Key for breadcrumb instance. Default value: default

### Return Values

No value is returned.

### **Examples**

```php
$tree_index = tree_index(dbquery_tree_full(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent'));
$tree_full = dbquery_tree_full(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
make_page_breadcrumbs($tree_index, $tree_full, 'news_cat_id', 'news_cat_name');
```

