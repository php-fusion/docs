---
description: Get the array of enabled languages.
---

# fusion\_get\_enabled\_languages\(\)

Versions: `9`

fusion\_get\_enabled\_languages\(\)

### Parameters <a id="parameters"></a>

No parameters.

### Return Values

\(array\)

### **Examples**

```php
$languages = fusion_get_enabled_languages();
if (count($languages) > 1) {
    foreach ($languages as $language_folder => $language_name) {
        //
    }
}
```

