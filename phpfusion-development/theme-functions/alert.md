---
description: Creates an alert bar.
---

# alert\(\)

Versions: `9`

alert\( string $title \[, array $options \] \) : string

### Parameters <a id="parameters"></a>

$title \(string\) \(Required\) Text inside the alert.

$options \(array\) \(Optional\) Default value: \[\]

| Name | Description | Default |
| :--- | :--- | :--- |
| class | CSS class. | alert-danger |
| dismiss | Enable dismissal of an alert. | false |

### Return Values

\(string\)

### **Examples**

```php
echo alert('This is a danger alert!');
// <div class='alert alert-danger'>This is a danger alert!</div>
```

