---
description: stripinput - Quote string with slashes
---

# addslash

`(Version 7)` `(Version 8)` `(Version 9)`

## Description

addslash`( string $value) : string`

PHPFusion implements a single sanitization method for simplicity purpose under the PHPFusion Defender class. Each method listed under this will fit a certain purpose.

Returns a string with blackslashes added before characters that are needed to be escaped. These characters are:

* single quote \('\)
* double quote \("\)
* blackslash \(\)
* NUL \(the NUL btye\)

A use case of **addslashes\(\)** is escaping the aforementioned characters in a string that is to be evaluated by PHP.

```text
<?php
$str = "O'Reilly?";
echo addslash($str); // O\'Reilly?
?>
```

**NOTE:** The addslash is an extension of addslashes with QUOTES\_GPC check. The addslashes\(\) is sometimes incorrectly used to try to prevent SQL injection. Instead database specific escaping functions and/or prepared statements should de used.

### Parameters

str The string to be escaped.

### Return Values

Returns the escaped string

