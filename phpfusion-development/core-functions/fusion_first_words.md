---
description: Trim a text to a number of words.
---

# fusion\_first\_words\(\)

Versions: `9`

fusion\_first\_words\( string $text, int $limit \[, string $suffix \] \) : string

### Parameters <a id="parameters"></a>

$text \(string\) \(Required\) String to trim.

$limit \(int\) \(Required\) The number of words.

$suffix \(string\) \(Optional\) If $text is longer than $limit, $suffix will be appended. Default value: &hellip;

### Return Values

\(string\) String trimmed to the given length.

### **Examples**

```php
$text = 'The big brown fox jumped over the lazy dog';
echo fusion_first_words($text, 5);
// The big brown fox jumped…
```

