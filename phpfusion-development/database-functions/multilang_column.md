---
description: Multilang column.
---

# multilang\_column\(\)

Versions: `9`

multilang\_column\( string $column \) : string

### Parameters <a id="parameters"></a>

$column \(string\) \(Required\)

### Return Values

\(string\)

### Examples

```php
$result = dbquery("
    SELECT * FROM ".DB_NEWS."
    WHERE ".multilang_column('news_subject')." = '".$data['news_subject']."'
");
```

