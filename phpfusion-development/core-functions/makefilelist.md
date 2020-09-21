---
description: Create a list of files or folders and store them in an array.
---

# makefilelist\(\)

Versions: `9`

makefilelist\( string $folder \[, string $filter, bool $sort, string $type, string $ext\_filter \] \)

### Parameters <a id="parameters"></a>

$folder \(string\) \(Required\) Path to folder

$filter \(string\) \(Optional\) The names of the filtered folders and files separated by "\|", false to use default filter

$sort \(bool\) \(Optional\) False if you don't want to sort the result

$type \(string\) \(Optional\) Possible values: 'files' to list files, 'folders' to list folders

$ext\_filter \(string\) \(Optional\) File extensions separated by "\|", only when $type is 'files'

### Return <a id="return"></a>

\(array\) Array of all items

### **Example**

```php
$infusions = makefilelist(INFUSIONS, FALSE, TRUE, 'folders');
foreach ($infusions as $folder) {
    //
}
```

