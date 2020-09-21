---
description: Highlights given words in string.
---

# highlight\_words\(\)

Versions: `9`

highlight\_words\( array $words, string $subject \)

### Parameters <a id="parameters"></a>

$words \(array\) \(Required\) The words to highlight

$subject \(string\) \(Required\) Text that contains a word \(s\) that should be highlighted

### Return <a id="return"></a>

\(string\) Words highlighted in the string

### **Example**

```php
$words = ['lemon', 'banana'];
$subject = 'banana, apple, orange and lemon';
echo highlight_words($words, $subject);
// <span style='background-color:yellow;color:#333;font-weight:bold;padding-left:2px;padding-right:2px'>banana</span>, apple, orange and <span style='background-color:yellow;color:#333;font-weight:bold;padding-left:2px;padding-right:2px'>lemon</span>
```

