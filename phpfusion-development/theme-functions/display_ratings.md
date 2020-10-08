---
description: Display ratings.
---

# display\_ratings\(\)

Versions: `9`

display\_ratings\( int $total\_sum, int $total\_votes \[, string $link, string $class, int $mode \] \) : string

## Parameters <a id="parameters"></a>

$total\_sum \(int\) \(Required\) Total number of ratings.

$total\_votes \(int\) \(Required\) Total number of votes.

$link \(string\) \(Optional\) Make item clickable. Default value: null

$class \(string\) \(Optional\) CSS class for the link. Default value: null

$mode \(int\) \(Optional\) Show 2 out of 10 or 2/10 rating. Possible value: 1, 2. Default value: 1

## Return Values

\(string\)

## Examples

```php
echo display_ratings(100, 60);
// 1.67 out of 60 ratings
```

