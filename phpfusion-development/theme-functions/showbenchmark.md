---
description: Show benchmark and database performance.
---

# showBenchmark\(\)

Versions: `9`

showBenchmark\( \[ bool $show\_sql\_performance, string $performance\_threshold \] \) : string

### Parameters <a id="parameters"></a>

$show\_sql\_performance \(bool\) \(Optional\) Set true to popup SQL analysis modal. Default value: false

$performance\_threshold \(string\) \(Optional\) Results that are slower than this value will be highlighted. Default value: '0.01'

### Return Values

\(string\)

### **Examples**

```php
echo showBenchmark();
// Render time: 0.07051 seconds | Average: 0.15208 (-0.32572) seconds
```

