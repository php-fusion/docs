---
description: Display a ratings form.
---

# showratings\(\)

Versions: `9`

showratings\( string $rating\_type, int $rating\_item\_id, string $rating\_link \) : string

## Parameters <a id="parameters"></a>

$rating\_type \(string\) \(Required\)

$rating\_item\_id \(int\) \(Required\) The item id you are rating.

$rating\_link \(string\) \(Required\) The link for the page which the rating is on.

## Return Values

\(string\)

## Examples

```php
require_once INCLUDES.'ratings_include.php';

showratings('A', $data['article_id'], INFUSIONS.'articles/articles.php?article_id='.$data['article_id']);
```

