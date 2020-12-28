---
description: Display image in colorbox.
---

# colorbox\(\)

Versions: `9`

colorbox\( string $img\_path, string $img\_title \[, bool $responsive, string $class, bool $as\_text \] \) : string

## Parameters <a id="parameters"></a>

$img\_path \(string\) \(Required\) The path to image.

$img\_title \(string\) \(Required\) Image title.

$responsive \(bool\) \(Optional\) Add img-responsive class. Default value: true

$class \(string\) \(Optional\) CSS class. Default value: ''

$as\_text \(bool\) \(Optional\) Show clickable text instead image. Default value: false

## Return Values

\(string\)

## Examples

```php
echo colorbox(IMAGES.'phpfusion-icon.png', 'Logo');
```

{% hint style="success" %}
This function can be overridden in your theme.
{% endhint %}

