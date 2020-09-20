---
description: Clean URL will clean the URL and prevents entities in server globals.
---

# cleanurl\(\)

Versions: `7`, `8`, `9`

cleanurl\( string $url \)

### Parameters <a id="parameters"></a>

$url \(string\) \(Required\) URL

### Return <a id="return"></a>

\(string\) $url clean and ready for use XHTML strict and without any dangerous code

### **Example**

```php
$url = 'http://www.test.com?this=that&that=this<&tagg>';
echo cleanurl($url);
// http://www.test.com?this=that&that=this&tagg
```

