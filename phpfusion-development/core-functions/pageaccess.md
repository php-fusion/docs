---
description: >-
  Check the user rights and redirect if the user does not have rights for the
  page.
---

# pageAccess\(\)

Versions: `9`

pageAccess\( string $rights \[, bool $debug \] \)

### Parameters <a id="parameters"></a>

$rights \(string\) \(Required\) Rights you want to check for the administrator.

$debug \(bool\) \(Optional\) For debugging purposes. Default value: false

### Return Values

No value is returned.

### **Examples**

```php
// Paste the code after maincore.php
pageAccess('I');
// If you do not have access to the Infusion administration, you will be redirected to the index
```

