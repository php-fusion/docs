---
description: >-
  Replace offensive words with the defined replacement word. The list of
  offensive words and the replacement word are both defined in the Security
  Settings.
---

# censorwords\(\)

Versions: `9`

censorwords\( string $text \) : bool

## Parameters <a id="parameters"></a>

$text \(string\) \(Required\) Text that should be censored.

## Return Values

\(bool\) Censored text.

## Examples

```php
// In this example we have added words apple and orange as offensive words and set replacement as ****
$text = 'The apple, orange and banana are all fruits.';
echo censorwords($text);
// The ****, **** and banana are all fruits.
```

