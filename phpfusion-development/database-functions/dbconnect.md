---
description: Connect to the database.
---

# dbconnect\(\)

Versions: `9`

dbconnect\( string $db\_host, string $db\_user, string $db\_pass, string $db\_name \[, int $db\_port, bool $halt\_on\_error \] \) : array

## Parameters <a id="parameters"></a>

$db\_host \(string\) \(Required\) The MySQL server.

$db\_user \(string\) \(Required\) The username.

$db\_pass \(string\) \(Required\) The password.

$db\_name \(string\) \(Required\) The name of the database that is to be selected.

$db\_port \(int\) \(Optional\) The TCP/IP port on which the MySQL server is listening. Default value: 3306

$halt\_on\_error \(bool\) \(Optional\) If it is true, the script will halt in case of error. Default value: false

## Return Values

\(array\) Returns a MySQL link identifier on success, or "Unable to establish connection to MySQL" on failure.

## Examples

```php
// Establish mySQL database connection
// The variables are stored in the config.php file
dbconnect($db_host, $db_user, $db_pass, $db_name);
```

