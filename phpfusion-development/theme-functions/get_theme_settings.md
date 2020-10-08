---
description: Fetch the settings from DB_SETTINGS_THEME.
---

# get\_theme\_settings\(\)

Versions: `9`

get\_theme\_settings\( string $theme\_folder \) : mixed

### Parameters <a id="parameters"></a>

$theme\_folder \(string\) \(Required\) The name of the theme folder.

### Return Values

\(array\|false\) Associative array of settings or false if is empty.

### Examples

```php
$theme_settings = get_theme_settings('my_theme');
echo $theme_settings['facebook_url'];
```

