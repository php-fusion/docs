# checkrights\(\)

Versions: `9`

checkrights\( string $rights \) : bool

### Parameters <a id="parameters"></a>

$rights \(string\) \(Required\) Rights you want to check for the administrator.

### Return Values

\(bool\) True if the user is administrator with rights defined in $rights.

### Examples

```php
if (checkrights('M')) {
    echo 'User has access to member management.';
}
```

