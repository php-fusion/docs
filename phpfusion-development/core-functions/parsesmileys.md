---
description: Parse the smileys in string and display smiley codes as smiley images.
---

# parsesmileys\(\)

Versions: `9`

parsesmileys\( string $message \) : string

## Parameters <a id="parameters"></a>

$message \(string\) \(Required\) A string that should have parsed smileys.

## Return Values

\(string\) String with parsed smiley codes as smiley images ready for display.

## Examples

```php
$message = "Here is a text :) with some smiley's in it :D.";
echo parsesmileys($message);
// Here is a text <img src='http://example.com/images/smiley/smile.svg' alt='Smile'> with some smiley's in it <img src='http://example.com/images/smiley/grin.svg' alt='Grin'>.
```

