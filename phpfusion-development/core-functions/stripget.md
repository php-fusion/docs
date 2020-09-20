---
description: Prevent any possible XSS attacks via $_GET.
---

# stripget\(\)

Versions: `7`, `8`, `9`

stripget\( string $check\_url \)

### Parameters <a id="parameters"></a>

$check\_url \(string\) \(Required\) string or array to be stripped

### Return <a id="return"></a>

\(bool\) TRUE if the URL is not secure

### **Example**

```php
if (stripget($_GET)) {
    //
}
```

### Notes

This function is used in maincore.php so basically there is no need to call this function manually.

