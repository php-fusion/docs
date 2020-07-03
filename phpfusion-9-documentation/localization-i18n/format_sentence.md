---
description: format_sentence - returns a quantitative sentence.
---

# format\_sentence

`(Version 9)` `(Version 10)`

## Description

format\_sentence

`( array $words) : string`

This function translates basic quantitative sentence, putting a comma before _and_ in a list. The sentence structure derives from a **series of commas** or **Oxford commas.** Basically, this means the formatter will provide a comma to each independent clauses before the word **and** before completing the sentence.

**Let us examine these examples and the code to achieve it.**  
  
**On Monday we’ll see the Eiffel Tower** and **on Tuesday we’ll visit the Louvre**.

```php
$word = array(
"On Monday we'll see the Eiffel Tower",
"on Tuesday we'll visit the Lourvre"
);
echo format_sentence($word);
```

**Sam, John, Peter and Sarah** take excellent care of their pets.

```php
$noun = array(
"Sam", "John", "Peter", "Sarah"
);
echo format_sentence($noun)." take excellent care of their pets";
```

### Return Values

Returns a quantitative sentence.

