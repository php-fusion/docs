---
description: Custom preg_match function.
---

# preg\_check\(\)

Versions: `9`

preg\_check\( string $expression, mixed $value \)

### Parameters <a id="parameters"></a>

$expression \(string\) \(Required\) The expression to search for

$value \(mixed\) \(Required\) The input string

### Return <a id="return"></a>

\(bool\) False when value is an array

### **Example**

```php
$value = 'abc123';
if (preg_check("/^[0-9A-Za-z]+$/", $value)) {
    echo 'String';
}
// String
```

