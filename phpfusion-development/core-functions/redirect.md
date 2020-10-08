---
description: Redirect to internal or external URL.
---

# redirect\(\)

Versions: `9`

redirect\( string $location \[, bool $delay, bool $script, int $code \] \) : void

## Parameters <a id="parameters"></a>

$location \(string\) \(Required\) Destination URL

$delay \(bool\) \(Optional\) Meta refresh delay. Default value: false

$script \(bool\) \(Optional\) Set true if you want to redirect via javascript. Default value: false

$code \(int\) \(Optional\) HTTP status code to send. Default value: 200

## Return Values

No value is returned.

## Examples

```php
redirect(BASEDIR.'page.php');
```

```php
redirect('http://example.com/');
```

