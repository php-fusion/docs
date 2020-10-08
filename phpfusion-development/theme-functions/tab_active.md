---
description: Current active tab selector.
---

# tab\_active\(\)

Versions: `9`

tab\_active\( array $array, int $default\_active \[, string $getname \] \) : string

## Parameters <a id="parameters"></a>

$array \(array\) \(Required\) Multidimension array consisting of keys title, id, icon.

$default\_active \(int\) \(Required\) 0 if link\_mode is false, $\_GET if link\_mode is true.

$getname \(string\) \(Optional\) Set getname and turn tabs into link that listens to getname. Default value: null

## Return Values

\(string\)

## Examples

```php
$tab_title['title'][] = 'Tab 1';
$tab_title['id'][] = 'tab1';
$tab_title['icon'][] = 'fa fa-cog';

$tab_title['title'][] = 'Tab 2';
$tab_title['id'][] = 'tab2';
$tab_title['icon'][] = 'fa fa-folder';

$tab_active = tab_active($tab_title, 0);

echo opentab($tab_title, $tab_active, 'testtab');

echo opentabbody($tab_title['title'][0], 'tab1', $tab_active);
echo 'Tab 1 content goes here';
echo closetabbody();

echo opentabbody($tab_title['title'][1], 'tab2', $tab_active);
echo 'Tab 2 content goes here';
echo closetabbody();

echo closetab();
```

