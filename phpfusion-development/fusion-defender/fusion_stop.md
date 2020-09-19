---
description: fusion_stop - declares FUSION_NULL constants to safeguard sensitive code execution.
---

# fusion\_stop

`(Version 9)` `(Version 10)`

## Description

fusion\_stop`( string $value) : string`

PHPFusion uses a `FUSION_NULL` constant to indicate there is a impending error that is going to happen soon to your system. This constant is used throughtout the entire system and fundamentally functions to complete the PHPFusion security feature ecosystem.

When validation fails in a particular subset of inputs, other functions built into deep sensing of the declaration of `FUSION_NULL` constant will stop its intended function execution. This is particularly useful when developers intend to stop something from happening should such constant is being declared.

Declares FUSION\_NULL in the PHPFusion system. Some of the important components that is built to sense `FUSION_NULL` are:

* dbquery\_insert
* fusion\_safe

An example implementation is to use `fusion_stop` to halt the system, and safeguarded by the `fusion_safe` function.

```php
<?php
$number = "Some bad input";
if (!isnum($number)) {
    fusion_stop("The \$number string must be a number.");
}
if (fusion_safe()) {
    // ... do something data sensitive like storage or callback
}
?>
```

### Parameters

$value The notification value. If present, will show a notice of the message on page load.

### Return Values

`FUSION_NULL`
