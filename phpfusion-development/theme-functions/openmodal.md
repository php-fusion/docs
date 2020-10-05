---
description: Creates modal.
---

# openmodal\(\)

Versions: `9`

openmodal\( string $id, string $title \[, array $options \] \) : string

### Parameters <a id="parameters"></a>

$id \(string\) \(Required\) Unique modal ID.

$title \(string\) \(Required\) Modal title.

$options \(array\) \(Optional\) Default value: \[\]

| Name | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| class | string | label-default | CSS class. |
| button\_id | string | '' | ID of the button that opens modal. |
| button\_class | string | '' | Class of the button that opens modal. |
| static | bool | false | Shows the modal when initialized. |
| hidden | bool | false | Force a modal to be hidden at default, you will need to add a jquery trigger $\('\#your\_modal\_id'\).modal\('show'\); manually. |

### Return Values

\(string\)

### **Examples**

```php
echo openmodal('test_modal', 'Title', ['button_id' => 'modal_testing']);
echo 'Content goes here';
echo closemodal();

echo '<button type="button" id="modal_testing">Open modal</button>';
```

{% hint style="info" %}
See also [closemodal\(\)](closemodal.md).
{% endhint %}

