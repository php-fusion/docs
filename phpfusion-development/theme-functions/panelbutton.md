---
description: Show the collapse or expand a button for panels which are collapsible.
---

# panelbutton\(\)

Versions: `9`

panelbutton\( string $state, string $bname \) : string

## Parameters <a id="parameters"></a>

$state \(string\) \(Required\) Panel state. Possible value: on, off

$bname \(string\) \(Required\) Button name.

## Return Values

\(string\)

## Examples

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

