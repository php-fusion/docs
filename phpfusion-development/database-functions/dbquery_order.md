---
description: Table rows ordering.
---

# dbquery\_order\(\)

Versions: `9`

dbquery\_order\( string $dbname, int $current\_order, string $order\_col \[, int $current\_id, string $id\_col, int $current\_category, string $cat\_col, bool $multilang, string $multilang\_col, string $mode \] \) : mixed

### Parameters <a id="parameters"></a>

$dbname \(string\) \(Required\) Table name.

$current\_order \(int\) \(Required\)

$order\_col \(string\) \(Required\)

$current\_id \(int\) \(Optional\) Default value: 0

$id\_col \(string\) \(Optional\) Default value: null

$current\_category \(int\) \(Optional\) Default value: 0

$cat\_col \(string\) \(Optional\) Default value: null

$multilang \(bool\) \(Optional\) Default value: false

$multilang\_col \(string\) \(Optional\) Default value: ''

$mode \(string\) \(Optional\) Possible value: save, update, delete. Default value: update

### Return Values

\(mixed\)

### Examples

```php
dbquery_order(DB_PHOTOS, $data['photo_order'], 'photo_order', $data['photo_id'], 'photo_id', NULL, NULL, FALSE, '', 'update');
```

