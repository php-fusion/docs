---
description: >-
  Closes an open side panel which is using the openside function. The function
  is defined in the theme.php and is different from theme to theme.
---

# closeside\(\)

Versions: `9`

closeside\( void \) : string

## Parameters <a id="parameters"></a>

No parameters.

## Return Values

\(string\)

## Examples

```php
function closeside() {
    echo '</div>'; // .panel-body
    echo '</div>'; // .panel
}
```

```php
openside('Title');
// Content goes here
closeside();
```

