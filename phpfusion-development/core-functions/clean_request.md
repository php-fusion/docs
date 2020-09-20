---
description: Generate a clean request URI.
---

# clean\_request\(\)

Versions: `9`

clean\_request\( \[ mixed $request\_addition, array $filter\_array, bool $keep\_filtered \] \)

### Parameters <a id="parameters"></a>

$request\_addition \(mixed\) \(Optional\) 'page=1&ref=2' or array\('page' =&gt; 1, 'ref' =&gt; 2\)

$filter\_array \(array\) \(Optional\) array\('aid', 'page', 'ref'\)

$keep\_filtered \(bool\) \(Optional\) True to keep filter, false to remove filter from FUSION\_REQUEST

### Return <a id="return"></a>

\(string\) Request URI

### **Example**

```php
// Original URI http://example.com/test.php?test=123
echo clean_request();
// /test.php
```

```php
// Original URI http://example.com/test.php?test=aaaa&this=123
echo clean_request('', ['test'], FALSE);
// /test.php?this=123
```

