---
description: >-
  Closes an main panel which is using the opentable function. The function is
  defined in the theme.php and is different from theme to theme.
---

# closetable\(\)

Versions: `9`

closetable\( void \) : string

## Parameters <a id="parameters"></a>

No parameters.

## Return Values

\(string\)

## Examples

```php
function closetable() {
    echo '</div>'; // .panel-body
    echo '</div>'; // .panel
}
```

```php
opentable('Title');
// Content goes here
closetable();
```

