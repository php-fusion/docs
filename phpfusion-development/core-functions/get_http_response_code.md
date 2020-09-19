---
description: Get HTTP response code
---

# get\_http\_response\_code\(\)

Versions: `9`

get\_http\_response\_code\(string $url\)

### Parameters <a id="parameters"></a>

$url \(string\) \(Required\) URL

### Return <a id="return"></a>

\(false\|string\)

### **Example**

```php
if (get_http_response_code('https://www.google.com/') == 200) {
    //
}
```

