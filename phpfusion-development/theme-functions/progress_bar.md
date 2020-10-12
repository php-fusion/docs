---
description: Display a progress bar.
---

# progress\_bar\(\)

Versions: `9`

progress\_bar\( mixed $num \[, string\|array $title, array $options \] \) : string

## Parameters <a id="parameters"></a>

$num \(int\) \(Required\) Max of 100 or array of numbers.

$title \(string\) \(Optional\) Label for the progress bar or array with multiple titles. Default value: null

$options \(array\) \(Optional\) Default value: \[\]

| Name | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| class | string | '' | Additional class for the progress bar. |
| height | string | 20px | The height of the progress bar in px. |
| reverse | bool | false | Set to true to have the color counting reversed. |
| as\_percent | bool | true | Show percentages. |
| disabled | bool | false | Set to true to have the progress bar disabled status. |
| hide\_info | bool | false | Set to true to hide the information in the progress bar rendering. |
| progress\_class | string | '' | Custom progress bar class with your own custom class. |

## Return Values

\(string\)

## Examples

```php
echo progress_bar(64);
/*
<div class='text-right m-b-10'><span class='pull-left'></span><span class='clearfix'>64%</span></div>
<div class='progress' style='height: 20px'>
<div class='progress-bar progress-bar-info' role='progressbar' aria-valuenow='64%' aria-valuemin='0' aria-valuemax='100' style='width: 64%'>
</div></div>
*/
```

```php
echo progress_bar([64, 55], ['Progress 1', 'Progress 2']);
```

{% hint style="success" %}
This function can be overridden in your theme.
{% endhint %}

