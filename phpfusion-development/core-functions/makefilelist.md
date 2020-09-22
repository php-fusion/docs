---
description: Create a list of files or folders and store them in an array.
---

# makefilelist\(\)

Versions: `9`

makefilelist\( string $folder \[, string $filter, bool $sort, string $type, string $ext\_filter \] \)

### Parameters <a id="parameters"></a>

$folder \(string\) \(Required\) Path to folder.

$filter \(string\) \(Optional\) The names of the filtered folders and files separated by "\|", false to use default filter. Default value: ''

$sort \(bool\) \(Optional\) False if you don't want to sort the result. Default value: true

$type \(string\) \(Optional\) Possible values: 'files' to list files, 'folders' to list folders. Default value: files

$ext\_filter \(string\) \(Optional\) File extensions separated by "\|", only when $type is 'files'. Default value: '''

### Return Values

\(array\) Array of all items.

### **Examples**

```php
$infusions = makefilelist(INFUSIONS, FALSE, TRUE, 'folders');
foreach ($infusions as $folder) {
    //
}
```

