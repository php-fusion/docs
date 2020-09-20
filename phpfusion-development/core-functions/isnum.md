---
description: Validate numeric input.
---

# isnum\(\)

Versions: `7`, `8`, `9`

isnum\( mixed $value \[, bool $decimal, bool $negative \] \)

### Parameters <a id="parameters"></a>

$value \(mixed\) \(Required\) The value to be checked

$decimal \(bool\) \(Optional\) Decimals

$negative \(bool\) \(Optional\) Negative numbers

### Return <a id="return"></a>

\(bool\) True if the value is a number

### **Example**

```php
$value = 'abc123';
if (isnum($value)) {
    echo 'This is a number.';
} else {
    echo 'This is not a number.';
}
// This is not a number.
```

