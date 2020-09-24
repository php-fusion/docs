---
description: >-
  Show smiley's button which will insert the smileys to the given textarea and
  form.
---

# displaysmileys\(\)

Versions: `9`

displaysmileys\( string $textarea \[, string $form \] \) : string

### Parameters <a id="parameters"></a>

$textarea \(string\) \(Required\) The id of the textarea.

$form \(string\) \(Optional\) The form id in which the textarea is located. Default value: inputform

### Return Values

\(string\) Option for users to insert smileys in a post by displaying the smiley's button.

### **Examples**

```php
echo openform('testform', 'post');
echo displaysmileys('test_textarea', 'testform');
echo form_textarea('test_textarea');
echo closeform();
```

