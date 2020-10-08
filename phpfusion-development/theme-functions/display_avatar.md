---
description: Show user avatar.
---

# display\_avatar\(\)

Versions: `9`

display\_avatar\( array $userdata, string $size \[, string $class, bool $link, string $img\_class, string $custom\_avatar \] \) : string

## Parameters <a id="parameters"></a>

$userdata \(array\) \(Required\) User data with user\_id, user\_name , user\_avatar, user\_status

$size \(string\) \(Required\) A size for CSS max-width and max-height.

$class \(string\) \(Optional\) CSS class for &lt;a&gt; tag. Default value: ''

$link \(bool\) \(Optional\) Wrap image with &lt;a&gt; tag. Default value: true

$img\_class \(string\) \(Optional\) CSS class for &lt;img&gt; tag. Default value: ''

$custom\_avatar \(string\) \(Optional\) The path to own default avatar. Default value: ''

## Return Values

\(string\)

## Examples

```php
$userdata = fusion_get_userdata();
echo display_avatar($userdata, '40px');
```

