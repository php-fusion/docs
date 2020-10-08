---
description: SQL statement helper to find values in between dots.
---

# in\_group\(\)

Versions: `9`

in\_group\( string $column\_name, string $value \[, string $delim \] \) : string

### Parameters <a id="parameters"></a>

$column\_name \(string\) \(Required\)

$value \(string\) \(Required\)

$delim \(string\) \(Optional\) Delimiter. Default value: ,

### Return Values

\(string\)

### Examples

```php
$result = dbquery("SELECT news_cat_id, news_cat_name, news_cat_language
    FROM ".DB_NEWS_CATS."
    ".(multilang_table('NS') ? "WHERE ".in_group('news_cat_language', LANGUAGE) : '')."
    ORDER BY news_cat_name
");
```

