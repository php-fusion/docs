---
description: 'Text with BBCodes, smileys and any special characters parsed to HTML.'
---

# parse\_textarea\(\)

Versions: `9`

parse\_textarea\( string $value \[, bool $parse\_smileys, bool $parse\_bbcode, bool $decode, string $default\_image\_folder, bool $add\_line\_breaks, bool $descript \] \)

### Parameters <a id="parameters"></a>

$value \(string\) \(Required\) String with unparsed text

$parse\_smileys \(bool\) \(Optional\) Smiley parsing

$parse\_bbcode \(bool\) \(Optional\) BBCode parsing

$decode \(bool\) \(Optional\) Decode HTML entities

$default\_image\_folder \(string\) \(Optional\) Image folder for parse\_imageDir\(\)

$add\_line\_breaks \(bool\) \(Optional\) Allows nl2br\(\)

$descript \(bool\) \(Optional\) Sanitize text

### Return <a id="return"></a>

\(string\) Parsed string

### **Example**

```php
$value = 'Text :D [url]http://example.com/[/url]';
echo parse_textarea($value, TRUE, TRUE, FALSE);
// Text <img src='http://example.com/images/smiley/grin.svg' alt='Grin'> <a href='http://example.com/'>http://example.com/</a>
```

