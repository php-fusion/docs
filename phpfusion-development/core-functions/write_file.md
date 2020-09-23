---
description: A wrapper function for file_put_contents with cache invalidation.
---

# write\_file\(\)

Versions: `9`

write\_file\( string $file, mixed $data \[, int $flags \] \)

### Parameters <a id="parameters"></a>

$file \(string\) \(Required\) File path.

$data \(mixed\) \(Required\) The data to write.

$flags \(int\) \(optional\) Default value: null

### Return Values

\(int\) Number of written bytes.

### **Examples**

```php
$data = 'data...';
write_file(BASEDIR.'test.txt', $data);
```

