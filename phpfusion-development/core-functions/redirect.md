---
description: Redirect to internal or external URL.
---

# redirect\(\)

Versions: `7`, `8`, `9`

redirect\( string $location \[, bool $delay, bool $script, int $code \] \)

### Parameters <a id="parameters"></a>

$location \(string\) \(Required\) Destination URL

$delay \(bool\) \(Optional\) Meta refresh delay

$script \(bool\) \(Optional\) Set true if you want to redirect via javascript

$code \(int\) \(Optional\) HTTP status code to send

### Return <a id="return"></a>

No value is returned

### **Example**

```php
redirect(BASEDIR.'page.php');
```

