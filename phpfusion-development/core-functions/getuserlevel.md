---
description: Get a user level's name by the numeric code of level.
---

# getuserlevel\(\)

Versions: `9`

getuserlevel\( int $userlevel \) : mixed

### Parameters <a id="parameters"></a>

$userlevel \(int\) \(Required\) Level code.

### Return Values

\(string\|null\) The name of the given user level, null if does not exist.

### Examples

```php
echo getuserlevel(-102);
// Administrator
```

{% hint style="info" %}
This function will not work on user group names, for that purpose we recommend you to use the [getgroupname\(\)](getgroupname.md).
{% endhint %}

