---
description: Prevent any possible XSS attacks via $_GET.
---

# stripget\(\)

Versions: `9`

stripget\( string $check\_url \) : bool

### Parameters <a id="parameters"></a>

$check\_url \(string\) \(Required\) String or array to be stripped.

### Return Values

\(bool\) True if the URL is not secure.

### Examples

```php
if (stripget($_GET)) {
    //
}
```

{% hint style="info" %}
This function is used in maincore.php so basically there is no need to call this function manually.
{% endhint %}

