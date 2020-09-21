---
description: Parse BBCodes in the given string.
---

# parseubb\(\)

Versions: `9`

parseubb\( string $text \[, string $selected, bool $descript \] \)

### Parameters <a id="parameters"></a>

$text \(string\) \(Required\) A string that contains the text to be parsed

$selected \(string\) \(Optional\) The names of the required BBCodes to parse, separated by "\|"

$descript \(bool\) \(Optional\) Sanitize text

### Return <a id="return"></a>

\(string\) Parsed string

### **Example**

```php
$text = 'This is [b]bold[/b] and this is [i]italic[/i]';
echo parseubb($text);
// This is <strong>bold</strong> and this is <i>italic</i>
```

```php
$text = 'This is [b]bold[/b] and this is [i]italic[/i]. [u]Underline[/u].';
echo parseubb($text, 'b|u');
// This is <strong>bold</strong> and this is [i]italic[/i]. <u>Underline</u>.
```

