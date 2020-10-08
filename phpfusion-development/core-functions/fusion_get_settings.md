---
description: Fetch the settings from DB_SETTINGS.
---

# fusion\_get\_settings\(\)

Versions: `9`

fusion\_get\_settings\( \[ string $key \] \) : mixed

## Parameters <a id="parameters"></a>

$key \(string\) \(Optional\) The key of one setting. Default value: null

## Return Values

\(array\|string\) Associative array of settings or one setting by key.

## Examples

```php
$settings = fusion_get_settings();
echo $settings['siteurl'];
// http://example.com/
```

