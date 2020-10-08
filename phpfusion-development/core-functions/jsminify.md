---
description: Minify JS code.
---

# jsminify\(\)

Versions: `9`

jsminify\( string $code \) : string

## Parameters <a id="parameters"></a>

$code \(string\) \(Required\) Unminified code.

## Return Values

\(string\) Minified code.

## Examples

```php
echo jsminify('
function myFunction(p1, p2) {
    return p1 * p2; // The function returns the product of p1 and p2
}
');
// function myFunction(p1,p2){return p1*p2}
```

