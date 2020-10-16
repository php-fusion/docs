---
description: >-
  Opens the main panel. The function is defined in the theme.php and is
  different from theme to theme.
---

# opentable\(\)

Versions: `9`

opentable\( string $title \[, mixed $... \] \) : string

## Parameters <a id="parameters"></a>

$title \(string\) \(Required\) Panel title.

$... \(mixed\) \(optional\) Zero or more parameters to be passed. You can add your own parameters to be used in the theme.

## Return Values

\(string\)

## Examples

```php
function opentable($title) {
    echo '<div class="panel panel-default">';

    echo '<div class="panel-heading">';
    echo '<h3>'.$title.'</h3>';
    echo '</div>';

    echo '<div class="panel-body">';
}
```

```php
opentable('Title');
// Content goes here
closetable();
```

