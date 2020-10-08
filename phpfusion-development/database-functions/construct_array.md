---
description: Shorthand to explode strings to array by using commas.
---

# construct\_array\(\)

Versions: `9`

construct\_array\( string $string \[, string $string2, string $delimiter \] \) : array

## Parameters <a id="parameters"></a>

$string \(string\) \(Required\)

$string2 \(string\) \(Optional\) Default value: null

$delimiter \(string\) \(Optional\) Default value: ,

## Return Values

\(array\)

## Examples

```php
$array = construct_array('a,b,c,d');
/*
Array
(
    [0] => a
    [1] => b
    [2] => c
    [3] => d
)
*/
```

