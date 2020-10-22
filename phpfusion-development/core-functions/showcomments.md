---
description: Display a comments form.
---

# showcomments\(\)

Versions: `9`

showcomments\( string $comment\_type, string $comment\_db, string $comment\_col, int $comment\_item\_id, string $clink \[, bool $ratings \] \): string

## Parameters <a id="parameters"></a>

$comment\_type \(string\) \(Required\)

$comment\_db \(string\) \(Required\) The database table where the item you want to comment on resides in.

$comment\_col \(string\) \(Required\) The field in the table which holds the id for the item you want to comment on.

$comment\_item\_id \(int\) \(Required\) The actual id to the item you are commenting on.

$clink \(string\) \(Required\) The actual id to the item you are commenting on.

$ratings \(bool\) \(Optional\) Display ratings. Default value: false

## Return Values

\(string\)

## Examples

```php
require_once INCLUDES.'comments_include.php';

showcomments('A', DB_ARTICLES, 'article_id', $data['article_id'], INFUSIONS.'articles/articles.php?article_id='.$data['article_id']);
```

