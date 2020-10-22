---
description: Format the date and time according to the site and user offset.
---

# showdate\(\)

Versions: `9`

showdate\( string $format, int $val \[, array $options \] \) : string

## Parameters <a id="parameters"></a>

$format \(string\) \(Required\) Possible value: shortdate, longdate, forumdate, newsdate or date pattern for the strftime.

$val \(int\) \(Required\) Unix timestamp.

$options \(array\) \(Optional\) Possible values tz\_override. Default value: \[\]

## Return Values

\(string\) String formatted according to the given format string. Month and weekday names and other language dependent strings respect the current locale set.

## Examples

```php
echo showdate('shortdate', time());
// 09/23/2020
```

```php
echo showdate('%d. %m. %Y', time());
// 23. 09. 2020
```

