---
description: Load any function and return it's value.
---

# fusion\_get\_function\(\)

Versions: `9`

openside \( string $function \[, mixed $... \] \) : mixed

## Parameters <a id="parameters"></a>

$function \(string\) \(Required\) Function name.

$... \(mixed\) \(optional\) Zero or more parameters to be passed, depending on function.

## Return Values

\(string\)

## Examples

```php
$html = fusion_get_function('opentable', 'Title');
```

