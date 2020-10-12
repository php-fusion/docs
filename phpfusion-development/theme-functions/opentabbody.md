---
description: Creates tab body.
---

# opentabbody\(\)

Versions: `9`

opentabbody\( string $tab\_title, string $tab\_id \[, string $link\_active\_arrkey, bool $link, string $key \] \) : string

## Parameters <a id="parameters"></a>

$tab\_title \(string\) \(Required\) Deprecated, for compatibility only.

$tab\_id \(string\) \(Required\) Tab id from $tab\_title\['id'\].

$link\_active\_arrkey \(string\) \(Required\) [tab\_active\(\)](tab_active.md) function or the $\_GET request to match the $tab\_title\['id'\].

$link \(bool\) \(Optional\) Deprecated, for compatibility only. False for jquery, true for php \(will reload page\). Default value: false

$key \(string\) \(Optional\) Set getname and turn tabs into link that listens to getname. Default value: section

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

{% hint style="success" %}
This function can be overridden in your theme.
{% endhint %}

