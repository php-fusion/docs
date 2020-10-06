---
description: Get maximum depth of a hierarchy tree.
---

# array\_depth\(\)

Versions: `9`

array\_depth\( array $array \) : int

### Parameters <a id="parameters"></a>

$array \(array\) \(Required\) Results from [dbquery\_tree\(\)](dbquery_tree.md).

### Return Values

\(int\)

### **Examples**

```php
$array = dbquery_tree(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent');
$array_depth = array_depth($array);
// 2
```

