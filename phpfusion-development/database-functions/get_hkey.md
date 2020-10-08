---
description: Get tree root ID of a child via SQL. Alternative function to get_root().
---

# get\_hkey\(\)

Versions: `9`

get\_hkey\( string $db, string $id\_col, string $cat\_col, int $current\_id \) : int

### Parameters <a id="parameters"></a>

$db \(string\) \(Required\) Table name.

$id\_col \(string\) \(Required\) ID column.

$cat\_col \(string\) \(Required\) Category column.

$current\_id \(string\) \(Required\) The current id of the item.

### Return Values

\(int\)

### Examples

```php
$root = get_hkey(DB_NEWS_CATS, 'news_cat_id', 'news_cat_parent', 1);
// 1
```

