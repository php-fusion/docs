---
description: Get color brightness by given HEX code.
---

# get\_color\_brightness\(\)

Versions: `9`

get\_color\_brightness\( string $hex \) : float

## Parameters <a id="parameters"></a>

$hex \(string\) \(Required\) HEX color code.

## Return Values

\(string\) Color brightness.

## Examples

```php
$text = 'String';
$hex = string_to_color_code($text); // a33297
$brightness = get_color_brightness($hex); // 95.301
$color = $brightness > 130 ? '000' : 'fff';
echo '<span style="background: #'.$hex.'; color: #'.$color.';">'.$text.'</span>';
// <span style="background: #a33297; color: #fff;">String</span>
```

