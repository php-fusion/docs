---
description: Show PHP-Fusion Performance.
---

# showrendertime\(\)

Versions: `9`

showrendertime\( \[ bool $queries \) : string

### Parameters <a id="parameters"></a>

$queries \(bool\) \(Optional\) The number of queries used on the current page. Default value: true

### Return Values

\(string\)

### **Examples**

```php
echo showrendertime();
// Render time: 0.06983 seconds | Average: 0.12833 (-0.02836) seconds | Queries: 32
```

