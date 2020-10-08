---
description: Create <option></option> from the entries in a given array.
---

# makefileopts\(\)

Versions: `9`

makefileopts\( array $options \[, string $selected \] \) : string

## Parameters <a id="parameters"></a>

$options \(array\) \(Required\) Options.

$selected \(string\) \(Optional\) The item in the options that you want to select by default. Default value: ''

## Return Values

\(string\) Array as a list of options for a select.

## Examples

```php
echo '<select>';
$options  = ['articles', 'news_cats', 'photoalbum'];
echo makefileopts($options);
echo '</select>';
/*
<select><option value='articles'>articles</option>
<option value='news_cats'>news_cats</option>
<option value='photoalbum'>photoalbum</option>
</select>
*/
```

