---
description: Creates a full page navigation used.
---

# makepagenav\(\)

Versions: `9`

makepagenav\( int $rowstart, int $count, int $total \[, int $range, string $link, string $getname, bool $button \] \)

### Parameters <a id="parameters"></a>

$rowstart \(int\) \(Required\) The number of the first listed item.

$count \(int\) \(Required\) The number of entries displayed on one page.

$total \(int\) \(Required\) The total entries which should be displayed.

$range \(int\) \(Optional\) The number of page buttons displayed and the range of them. Default value: 3

$link \(string\) \(Optional\) The base url before the appended part. Default value: ''

$getname \(string\) \(Optional\) The name of the $\_GET parameter that contains the start number. Default value: rowstart

$button \(bool\) \(Optional\) Displays as button. Default value: false

### Return Values

\(string\|bool\) HTML navigation. False if $count is invalid.

### **Examples**

```php
$limit = 15;
$total_rows = dbcount("(download_id)", DB_DOWNLOADS);
$rowstart = isset($_GET['rowstart']) && isnum($_GET['rowstart']) && ($_GET['rowstart'] <= $total_rows) ? $_GET['rowstart'] : 0;

$result = dbquery("SELECT *
    FROM ".DB_DOWNLOADS." 
    ORDER BY download_datestamp DESC LIMIT $rowstart, $limit
");

echo makepagenav($rowstart, $limit, $total_rows);
/*
<nav><small class='m-r-10'><span>Page </span> 1 of 2</small> <div class='btn-group'>
<a class='btn btn-sm btn-default active' href='page.php?rowstart=0'><strong>1</strong></a>
<a class='btn btn-sm btn-default' data-value='15' href='page.php?rowstart=15'>2</a>
</div></nav>
*/
```

