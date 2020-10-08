---
description: Fetch a locales.
---

# fusion\_get\_locale\(\)

Versions: `9`

fusion\_get\_locale\( \[ string $key, mixed $include\_file \] \) : mixed

### Parameters <a id="parameters"></a>

$key \(string\) \(Optional\) The key of one locale. Default value: null

$include\_file \(string\|array\) \(Optional\) The full path of the file which to be included. Default value: ''

### Return Values

\(array\|string\) Associative array of locales or one locale by key.

### Examples

```php
$locale = fusion_get_locale();
echo $locale['welcome'];
// Welcome back
```

{% hint style="info" %}
The global.php file is loaded automatically.
{% endhint %}

