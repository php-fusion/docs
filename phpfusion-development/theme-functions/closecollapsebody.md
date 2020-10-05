---
description: Close collapsing panel.
---

# closecollapsebody\(\)

Versions: `9`

closecollapsebody\( void \) : string

### Parameters <a id="parameters"></a>

No parameters.

### Return Values

\(string\)

### **Examples**

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

{% hint style="info" %}
See also [opencollapse\(\)](opencollapse.md).

See also [opencollapsebody\(\)](opencollapsebody.md).

See also [closecollapse\(\)](closecollapse.md).
{% endhint %}

