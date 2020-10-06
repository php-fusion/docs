---
description: MYSQL show columns shorthand.
---

# fieldgenerator\(\)

Versions: `9`

fieldgenerator\( string $db \) : array

### Parameters <a id="parameters"></a>

$db \(string\) \(Required\) Table name.

### Return Values

\(array\)

### **Examples**

```php
$fields = fieldgenerator(DB_NEWS_CATS);
/*
Array
(
    [0] => news_cat_id
    [1] => news_cat_parent
    [2] => news_cat_name
    [3] => news_cat_image
    [4] => news_cat_visibility
    [5] => news_cat_draft
    [6] => news_cat_sticky
    [7] => news_cat_language
)
*/
```

