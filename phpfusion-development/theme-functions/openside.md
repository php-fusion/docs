---
description: >-
  Opens the side panel. The function is defined in the theme.php and is
  different from theme to theme.
---

# openside\(\)

Versions: `9`

openside \( string $title \[, string $class, mixed $... \] \) : string

## Parameters <a id="parameters"></a>

$title \(string\) \(Required\) Panel title.

$class \(string\) \(optional\) CSS class. Default value: ''

$... \(mixed\) \(optional\) Zero or more parameters to be passed. You can add your own parameters to be used in the theme.

## Return Values

\(string\)

## Examples

```php
function openside($title = FALSE, $class = '') {
    echo '<div class="panel panel-default '.$class.'">';

    echo '<div class="panel-heading">';
    echo $title;
    echo '</div>';

    echo '<div class="panel-body">';
}
```

```php
openside('Title');
// Content goes here
closeside();
```

