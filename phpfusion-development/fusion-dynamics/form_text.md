---
description: Generates a text input.
---

# form\_text\(\)

Versions: `9`

form\_text\( string $input\_name \[, string $label, string $input\_value, array $options \] \) : string

### Parameters <a id="parameters"></a>

$input\_name \(string\) \(Required\) Name of the input, by
 default it's also used as the ID for the input.

$label \(string\) \(Optional\) Input label. Default value: ''

$input\_value \(string\) \(Optional\) The value to be displayed. Default value: ''

$options \(array\) \(Optional\) Default value: \[\]

| Name | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| type | string | text | Possible value: text, number, password, email, url, color, date, datetime, datetime-local, month, range, search, tel, time, week. |
| required | bool | false | Whether this field is required during form submission. |
| label\_icon | string | '' |  |
| feedback\_icon | string | '' |  |
| safemode | bool | false |  |
| regex | string | '' |  |
| regex\_error\_text | string | '' |  |
| callback\_check | bool | false |  |
| input\_id | string | $input\_name |  |
| placeholder | string | '' | A placeholder for the field. |
| deactivate | bool | false | Disable the input and set it as readonly. |
| width | string | '' | Accepts px or % values. |
| inner\_width | string | '' | Accepts px or % values. |
| class | string | '' |  |
| inner\_class | string | '' |  |
| inline | bool | false |  |
| min\_length | int | 1 |  |
| max\_length | int | 200 |  |
| number\_min | int | 0 |  |
| number\_max | int | 0 |  |
| number\_step | int | 1 |  |
| icon | string | '' |  |
| autocomplete\_off | bool | false |  |
| tip | string | '' | Displays a tip by the label. |
| ext\_tip | string | '' | Displays a tip at the bottom of the input. |
| append\_button | bool | false |  |
| append\_value | string | '' |  |
| append\_form\_value | string | '' |  |
| append\_size | string | '' |  |
| append\_class | string | btn-default |  |
| append\_type | string | submit |  |
| append\_id | string | p-{input\_id}-append |  |
| append\_button\_name | string | p-submit-{input\_id}-append |  |
| append\_button\_id | string | {input\_id}-append-btn |  |
| prepend\_button | bool | false |  |
| prepend\_value | string | '' |  |
| prepend\_form\_value | string | '' |  |
| prepend\_size | string | '' |  |
| prepend\_class | string | btn-default |  |
| prepend\_type | string | submit |  |
| prepend\_id | string | p-{input\_id}-prepend |  |
| prepend\_button\_name | string | p-submit-{input\_id}-prepend |  |
| prepend\_button\_id | string | {input\_id}-prepend-btn |  |
| error\_text | string | '' |  |
| delimiter | string | , |  |
| stacked | string | '' |  |
| group\_size | string | '' | Possible value: sm, md, lg |
| password\_strength | bool | false |  |
| data | array | \[\] |  |
| append\_html | string | '' |  |
| censor\_words | bool | true |  |
| password\_toggle | bool | true |  |
| descript | bool | true |  |

### Return Values

\(string\)

### Examples

```php
echo form_text('text_field', 'Text Field');
```

