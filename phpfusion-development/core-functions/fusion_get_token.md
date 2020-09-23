---
description: Get form tokens.
---

# fusion\_get\_token\(\)

Versions: `9`

fusion\_get\_token\( string $form\_id \[, int $max\_tokens \] \)

### Parameters <a id="parameters"></a>

$form\_id \(string\) \(Required\) Form ID.

$max\_tokens \(int\) \(Optional\) Max tokens. Default value: 5

### Return Values

\(string\)

### **Examples**

```php
echo fusion_get_token('fusionform', 5);
// 1-1600889268-e2f1342970bae8a8db5e767e7c004ed5a72558c82ba
```

