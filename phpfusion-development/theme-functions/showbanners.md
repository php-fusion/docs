---
description: Display the site banner you specify through the Banner Management.
---

# showbanners\(\)

Versions: `9`

showbanners\( \[ int $display \] \) : string

## Parameters <a id="parameters"></a>

$display \(int\) \(Optional\) Possible value: 1, 2. If empty it shows banner 1. Default value: null

## Return Values

\(string\)

## Examples

```php
echo showbanners();
// Banner 1 content
echo showbanners(2);
// Banner 2 content
```

