---
description: Fetch one row as a numeric array.
---

# dbarraynum\(\)

Versions: `9`

dbarraynum\( mixed $result \) : array

### Parameters <a id="parameters"></a>

$result \(string\) \(Required\) The query resource that is being evaluated. This result comes from a call to [dbquery\(\)](dbquery.md).

### Return Values

\(array\) Returns an numerical array of strings that corresponds to the fetched row.

### **Examples**

```php
$result = dbquery("SELECT * FROM ".DB_TABLE);
if (dbrows($result) > 0) {
    while ($data = dbarraynum($result)) {
        //
    }
}
```

{% hint style="info" %}
See also [dbquery\(\)](dbquery.md).

See also [dbrows\(\)](dbrows.md).
{% endhint %}

