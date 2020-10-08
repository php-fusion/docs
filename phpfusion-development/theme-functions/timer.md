---
description: Show time ago from timestamp.
---

# timer\(\)

Versions: `9`

timer\( \[ int $time \] \) : string

### Parameters <a id="parameters"></a>

$time \(int\) \(Optional\) Timestamp or if empty it use time\(\). Default value: null

### Return Values

\(string\)

### Examples

```php
echo timer(1050149787);
// <abbr class='atooltip' data-toggle='tooltip' data-placement='top' title='April 12 2003 14:16:27'>17 years ago</abbr>
```

