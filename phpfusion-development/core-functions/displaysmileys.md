---
description: >-
  Show smiley's button which will insert the smileys to the given textarea and
  form.
---

# displaysmileys\(\)

Versions: `7`, `8`, `9`

displaysmileys\( string $textarea \[, string $form \] \)

### Parameters <a id="parameters"></a>

$textarea \(string\) \(Required\) The id of the textarea

$form \(string\) \(Optional\) The form id in which the textarea is located

### Return <a id="return"></a>

\(string\) This function will return the option for users to insert smiley's in a post by displaying the smiley's BBCode button.

### **Example**

```php
echo openform('testform', 'post');
echo displaysmileys('test_textarea', 'testform');
echo form_textarea('test_textarea');
echo closeform();
```

