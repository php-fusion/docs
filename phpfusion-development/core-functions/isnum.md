---
description: Validate numeric input.
---

# isnum\(\)

Versions: `9`

isnum\( mixed $value \[, bool $decimal, bool $negative \] \)

### Parameters <a id="parameters"></a>

$value \(mixed\) \(Required\) The value to be checked.

$decimal \(bool\) \(Optional\) Decimals. Default value: false

$negative \(bool\) \(Optional\) Negative numbers. Default value: false

### Return Values

\(bool\) True if the value is a number.

### **Examples**

```php
$value = 'abc123';
if (isnum($value)) {
    echo 'This is a number.';
} else {
    echo 'This is not a number.';
}
```

