---
description: Get currency symbol by using a 3-letter ISO 4217 currency code.
---

# fusion\_get\_currency\(\)

Versions: `9`

fusion\_get\_currency\(string $iso = NULL, bool $description = TRUE\)

### Parameters <a id="parameters"></a>

$iso \(string\) \(Optional\) 3-letter ISO 4217

$description \(bool\) \(Optional\) set to false for just symbol

### Return <a id="return"></a>

\(array\|string\) Array of currencies or string with one currency

###  **Example**

```php
echo fusion_get_currency('EUR'); // Euro (€)
```

