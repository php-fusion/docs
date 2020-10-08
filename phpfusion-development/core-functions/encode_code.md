---
description: Encode and format code inside <code> tag.
---

# encode\_code\(\)

Versions: `9`

encode\_code\( string $text \) : string

## Parameters <a id="parameters"></a>

$text \(string\) \(Required\) String with code.

## Return Values

\(string\) Encoded and formatted code.

## Examples

```php
$text = '<code><!DOCTYPE html>
    <html>
    <head>
        Test
    </head>
    <body>
        code
    </body>
</html></code>';
echo encode_code($text);
/*
<pre><code>&lt;!DOCTYPE html&gt;
&nbsp; &nbsp; &lt;html&gt;
&nbsp; &nbsp; &lt;head&gt;
&nbsp; &nbsp; &nbsp; &nbsp; Test
&nbsp; &nbsp; &lt;/head&gt;
&nbsp; &nbsp; &lt;body&gt;
&nbsp; &nbsp; &nbsp; &nbsp; code
&nbsp; &nbsp; &lt;/body&gt;
&lt;/html&gt;</code></pre>
*/
```

