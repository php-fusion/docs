---
description: Creates badge.
---

# badge\(\)

Versions: `9`

badge\( string $label \[, array $options \] \) : string

## Parameters <a id="parameters"></a>

$label \(string\) \(Required\) Text inside the label.

$options \(array\) \(Optional\) Default value: \[\]

| Name | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| class | string | '' | CSS class. |
| icon | string | '' | Icon CSS class. Eg. fa fa-beer. |

## Return Values

\(string\)

## Examples

```php
echo badge('Badge');
// <span class='badge'>Badge</span>
```

{% hint style="success" %}
This function can be overridden in your theme.
{% endhint %}

