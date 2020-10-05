---
description: Fetch one row as an associative array.
---

# dbarray\(\)

Versions: `9`

dbarray\( mixed $result \) : array

### Parameters <a id="parameters"></a>

$result \(string\) \(Required\) The query resource that is being evaluated. This result comes from a call to [dbquery\(\)](dbquery.md).

### Return Values

\(array\) Returns an associative array of strings that corresponds to the fetched row.

### **Examples**

```php
$result = dbquery("SELECT * FROM ".DB_TABLE);
if (dbrows($result) > 0) {
    while ($data = dbarray($result)) {
        //
    }
}
```

{% hint style="info" %}
See also [dbquery\(\)](dbquery.md).

See also [dbrows\(\)](dbrows.md).
{% endhint %}

