---
description: Get HTTP response code.
---

# get\_http\_response\_code\(\)

Versions: `9`

get\_http\_response\_code\( string $url \)

### Parameters <a id="parameters"></a>

$url \(string\) \(Required\) URL.

### Return Values

\(bool\|string\)

### **Examples**

```php
$url = 'https://www.google.com/';
if (get_http_response_code($url) == 200) {
    //
}
```

