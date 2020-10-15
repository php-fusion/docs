---
description: To flatten any multidimensional array.
---

# flatten\_array\(\)

Versions: `9`

flatten\_array\( array $array \) : array

## Parameters <a id="parameters"></a>

$array \(array\) \(Required\) Multidimensional array.

## Return Values

\(array\)

## Examples

```php
$array[] = [
    'title' => 'Test',
    'page'  => 2
];
$array = flatten_array($array);
/*
Array
(
    [title] => Test
    [page] => 2
)
*/
```

