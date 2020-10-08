---
description: Returns a grammatical number word.
---

# format\_word\(\)

Versions: `9`

format\_word\( int $count, string $words \[, array $options \] \) : string

## Parameters <a id="parameters"></a>

$count \(int\) \(Required\)

$words \(string\) \(Required\) A string consisting of singular and plural delimited by a \| symbol.

$options \(array\) \(Optional\) Default value: \[\]

| Name | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| add\_count | bool | true | Show number. |
| html | bool | false | Encase result with html\_template, {%count%} {%result%} tags are used for placeholders for result replacements. |
| html\_template | string | &lt;span class='fusion\_count'&gt;{%count%}&lt;/span&gt; &lt;span class='fusion\_word'&gt;{%result%}&lt;/span&gt; | HTML template to be used for output. |
| language | string | LANGUAGE | Current language. |

## Return Values

\(string\)

## Examples

```php
$array = [
    'Apple', 'Orange'
];
$count = count($array);
echo format_word($count, 'fruit|fruits');
// 2 fruits
```

