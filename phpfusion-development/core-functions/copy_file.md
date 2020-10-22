---
description: Copy a file from any source to any destination.
---

# copy\_file\(\)

Versions: `9`

copy\_file\( string $source, string $destination \) : mixed

## Parameters <a id="parameters"></a>

$source \(string\) \(Required\) Copy file from URL

$destination \(string\) \(Required\) Destination folder.

## Return Values

\(mixed\)

## Examples

```php
require_once INCLUDES.'photo_functions_include.php';

copy_file(IMAGES.'php-fusion-logo.png', IMAGES.'avatars/');
```

