---
description: format_word - returns a grammatical number word
---

# format\_word

`(Version 9)` `(Version 10)`

## Description

> format\_word \( int`$number` , string`$nouns` \[, array `$options` \] \) : string

**format\_word\(\)** returns a grammatical number word string from the $noun used as arguments for the callback. 

#### **Parameters**

`number`

A number

`nouns`

A string consisting of singular and plural delimited by a **`|`** symbol.

#### Return Values

Return a string of words with a correct grammatical word.  

#### Examples \#1 - counting a noun

```php
$array = array(
"Apple", "Orange"
);
$count = count($array);
echo format_word($count, "fruit|fruits"); // Returns "2 fruits"
```

#### Example \#2 - generate a sentence dynamically

```php
$array = array(
"Sam", "Peter", "Mary"
);
$count = count($array);
echo format_sentence($array)." ".format_word($count, "is|are")." going to the party.";
```

