---
description: Returns a string of quantitative sentence from an array.
---

# format\_sentence\(\)

Versions: `9`

format\_sentence\( array $words \) : string

This function translates basic quantitative sentence, putting a comma before and in a list. The sentence structure derives from a series of commas or Oxford commas. Basically, this means the formatter will provide a comma to each independent clauses before the word and before completing the sentence.

## Parameters <a id="parameters"></a>

$words \(array\) \(Required\)

## Return Values

\(string\)

## Examples

```php
$array = [
    'Sam', 'John', 'Peter', 'Sarah'
];
echo format_sentence($array).' take excellent care of their pets.';
// Sam, John, Peter and Sarah take excellent care of their pets.
```

