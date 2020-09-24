---
description: Sanitize text and remove potentially dangerous HTML and JavaScript.
---

# descript\(\)

Versions: `9`

descript\( string $text \[, bool $strip\_tags, bool $strip\_scripts \] \) : string

### Parameters <a id="parameters"></a>

$text \(string\) \(Required\) String to be descripted.

$strip\_tags \(bool\) \(Optional\) Removes potentially dangerous HTML tags. Default value: true

$strip\_scripts \(bool\) \(Optional\) Removes &lt;script&gt; tags. Default value: true

### Return Values

\(string\) Sanitized and safe string.

### **Examples**

```php
$text = 'Text <a href="javascript:function()">click</a> <i onload=xss></i> <script>javascript code</script>';
echo descript($text);
// Text &lt;a href=&quot;nojavascript...function()&quot;&gt;click&lt;/a&gt; &lt;i &gt;&gt;&lt;/i&gt; javascript code
```

