---
description: Prints human-readable information about a variable.
---

# print\_p\(\)

Versions: `9`

print\_p\( mixed $data \[, bool $modal, bool $print \] \) : string

### Parameters <a id="parameters"></a>

$data \(mixed\) \(Required\) The expression to be printed.

$modal \(bool\) \(Optional\) Dump info in the modal. Default value: false

$print \(bool\) \(Optional\) Dump info in &lt;pre&gt; tag. Default value: true

### Return Values

\(string\) The value of the variable.

### **Examples**

```php
$data = [
    'key'  => 67485,
    'key2' => 'value',
    'key3' => 4655
];
print_p($data);

/*
Array
(
    [key] => 67485
    [key2] => value
    [key3] => 4655
)
*/
```

