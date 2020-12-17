---
description: Declares FUSION_NULL constants to safeguard sensitive code execution.
---

# fusion\_stop\(\)

Versions: `9`

fusion\_stop\( \[ string $notice \] \) : void

PHPFusion uses a FUSION\_NULL constant to indicate there is a impending error that is going to happen soon to your system. This constant is used throughtout the entire system and fundamentally functions to complete the PHPFusion security feature ecosystem.

When validation fails in a particular subset of inputs, other functions built into deep sensing of the declaration of FUSION\_NULL constant will stop its intended function execution. This is particularly useful when developers intend to stop something from happening should such constant is being declared.

Declares FUSION\_NULL in the PHPFusion system. Some important components that is built to sense FUSION\_NULL are: dbquery\_insert\(\) and fusion\_safe\(\)

## Parameters <a id="parameters"></a>

$notice \(string\) \(Optional\) The notification text. If present, will show a notice on page load. Default value: null

## Return Values

No value is returned.

## Examples

An example implementation is to use fusion\_stop\(\) to halt the system, and safeguarded by the fusion\_safe\(\) function.

```php
if (!isnum('Some bad input')) {
    fusion_stop('The $number string must be a number.');
}

if (fusion_safe()) {
    // ... do something data sensitive like storage or callback
}
```

