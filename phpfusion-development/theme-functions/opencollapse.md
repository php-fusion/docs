---
description: Create accordion.
---

# opencollapse\(\)

Versions: `9`

opencollapse\( string $id \) : string

## Parameters <a id="parameters"></a>

$id \(string\) \(Required\) Unique accordion ID.

## Return Values

\(string\)

## Examples

```php
$collapse_id = 'test-group';
echo opencollapse($collapse_id);

echo opencollapsebody('Test 1', 'panel1', $collapse_id);
echo 'Content goes here';
echo closecollapsebody();

echo opencollapsebody('Test 2', 'panel2', $collapse_id, true); // this panel will be open
echo 'Content goes here';
echo closecollapsebody();

echo closecollapse();
```

{% hint style="success" %}
This function can be overridden in your theme.
{% endhint %}

