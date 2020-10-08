---
description: 'Translate bytes into kB, MB, GB or TB.'
---

# parsebytesize\(\)

Versions: `9`

parsebytesize\( int $size, int $decimals \[, bool $dir \] \) : string

## Parameters <a id="parameters"></a>

$size \(int\) \(Required\) The number of bytes.

$decimals \(int\) \(Optional\) The number of decimals. Default value: 2

$dir \(bool\) \(Optional\) True if it is the size of a directory. Default value: false

## Return Values

\(string\)

## Examples

```php
echo parsebytesize(52428800);
// 50MB
```

