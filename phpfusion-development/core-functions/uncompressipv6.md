---
description: Convert a shortened IPv6 address to its full length form.
---

# uncompressIPv6\(\)

Versions: `9`

uncompressIPv6\( string $ip \[, int $count \] \) : string

## Parameters <a id="parameters"></a>

$ip \(string\) \(Required\) IPv6 address to convert.

$count \(int\) \(Optional\) This parameter shows how many : are in the full length version.

## Return Values

\(string\)

## Examples

```php
echo uncompressIPv6('ABCD:123:45::9');
// ABCD:0123:0045:0000:0000:0000:0000:0009
```
