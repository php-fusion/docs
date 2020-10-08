---
description: Checks the state of a panel.
---

# panelstate\(\)

Versions: `9`

panelstate\( string $state, string $bname \[, string $element \] \) : string

### Parameters <a id="parameters"></a>

$state \(string\) \(Required\) Panel state. Possible value: on, off

$bname \(string\) \(Required\) Button name.

$element \(string\) \(Optional\) Element name. Default value: div

### Return Values

\(string\)

### Examples

```php
function openside($title = FALSE, $class = '', $state = 'on') {
    $boxname = str_replace(' ', '', $title);

    echo '<div class="panel panel-default '.$class.'">';

    echo '<div class="panel-heading">';
        echo $title;
        echo '<div class="pull-right">'.panelbutton($state, $boxname).'</div>';
    echo '</div>';

    echo panelstate($state, $boxname);

    echo '<div class="panel-body">';
}

function closeside() {
    echo '</div>'; // .panel-body
    echo '</div>'; // panelstate()

    echo '</div>'; // .panel
}
```

```php
openside('Title');
echo 'Content goes here';
closeside();
```

