---
description: Check if a given language is valid or if exists.
---

# valid\_language\(\)

Versions: `9`

valid\_language\( string $lang \[, bool $file\_check \] \)

### Parameters <a id="parameters"></a>

$lang \(string\) \(Required\) The name of the language.

$file\_check \(bool\) \(Optional\) Intended to be used when enabling languages in Admin Panel. Default value: false

### Return Values

\(bool\)

### **Examples**

```php
if (valid_language('English')) {
    echo 'The language is valid and ready to use.';
}
```

