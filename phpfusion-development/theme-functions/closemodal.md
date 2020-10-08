---
description: Close the modal.
---

# closemodal\(\)

Versions: `9`

closemodal\( void \) : string

### Parameters <a id="parameters"></a>

No parameters.

### Return Values

\(string\)

### Examples

```php
echo openmodal('test_modal', 'Title', ['button_id' => 'modal_testing']);
echo 'Content goes here';
echo closemodal();

echo '<button type="button" id="modal_testing">Open modal</button>';
```

