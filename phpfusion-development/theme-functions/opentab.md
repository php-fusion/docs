---
description: Creates tabs.
---

# opentab\(\)

Versions: `9`

opentab\( array $tab\_title, string $link\_active\_arrkey, string $id \[, bool $link, string $class, string $getname, array $cleanup\_GET, bool $remember \] \) : string

### Parameters <a id="parameters"></a>

$tab\_title \(array\) \(Required\) Multidimension array consisting of keys title, id, icon.

$link\_active\_arrkey \(string\) \(Required\) [tab\_active\(\)](tab_active.md) function or the $\_GET request to match the $tab\_title\['id'\].

$id \(string\) \(Required\) Unique ID.

$link \(bool\) \(Optional\) False for jquery, true for php \(will reload page\). Default value: false

$class \(string\) \(Optional\) CSS class for the nav. Default value: ''

$getname \(string\) \(Optional\) Set getname and turn tabs into link that listens to getname. Default value: section

$cleanup\_GET \(array\) \(Optional\) The request key that needs to be deleted. Default value: \[\]

$remember \(bool\) \(Optional\) Set to true to automatically remember tab using cookie. Default value: false

### Return Values

\(string\)

### **Examples**

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

