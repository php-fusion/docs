---
description: Display comments.
---

# display\_comments\(\)

Versions: `9`

display\_comments\( int $total\_sum \[, string $link, string $class, int $mode \] \) : string

## Parameters <a id="parameters"></a>

$total\_sum \(int\) \(Required\) Total number of comments.

$link \(string\) \(Optional\) Make item clickable. Default value: null

$class \(string\) \(Optional\) CSS class for the link. Default value: null

$mode \(int\) \(Optional\) Show 2 out of 10 or 2/10 comments. Possible value: 1, 2. Default value: 1

## Return Values

\(string\)

## Examples

```php
echo display_comments(100);
// 100 comments
```

