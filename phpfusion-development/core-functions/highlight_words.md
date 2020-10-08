---
description: Highlights given words in string.
---

# highlight\_words\(\)

Versions: `9`

highlight\_words\( array $words, string $subject \) : string

## Parameters <a id="parameters"></a>

$words \(array\) \(Required\) The words to highlight.

$subject \(string\) \(Required\) Text that contains a word \(s\) that should be highlighted.

## Return Values

\(string\) Words highlighted in the string.

## Examples

```php
$words = ['lemon', 'banana'];
$subject = 'banana, apple, orange and lemon';
echo highlight_words($words, $subject);
// <span style='background-color:yellow;color:#333;font-weight:bold;padding-left:2px;padding-right:2px'>banana</span>, apple, orange and <span style='background-color:yellow;color:#333;font-weight:bold;padding-left:2px;padding-right:2px'>lemon</span>
```

