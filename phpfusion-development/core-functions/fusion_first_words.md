---
description: Trim a text to a number of words.
---

# fusion\_first\_words\(\)

Versions: `9`

fusion\_first\_words\( string $text, int $limit \[, string $suffix \] \)

### Parameters <a id="parameters"></a>

$text \(string\) \(Required\) String to trim

$limit \(int\) \(Required\) The number of words

$suffix \(string\) \(Optional\) If $text is longer than $limit, $suffix will be appended

### Return <a id="return"></a>

\(string\) String trimmed to the given length

### **Example**

```php
$text = 'The big brown fox jumped over the lazy dog';
echo fusion_first_words($text, 5);
// The big brown fox jumped…
```

