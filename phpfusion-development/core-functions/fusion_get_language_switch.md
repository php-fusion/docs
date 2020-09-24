---
description: Get language switch arrays.
---

# fusion\_get\_language\_switch\(\)

Versions: `9`

fusion\_get\_language\_switch\( void \) : array

### Parameters <a id="parameters"></a>

No parameters.

### Return Values

\(array\)

### **Examples**

```php
$language_switch = fusion_get_language_switch();
if (!empty($language_switch)) {
    foreach ($language_switch as $folder => $langData) {
        //
    }
}
```

