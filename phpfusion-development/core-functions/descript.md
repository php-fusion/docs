---
description: Sanitize text and remove potentially dangerous HTML and JavaScript.
---

# descript\(\)

Versions: `9`

descript\( string $text \[, bool $strip\_tags, bool $strip\_scripts \] \)

### Parameters <a id="parameters"></a>

$text \(string\) \(Required\) String to be descripted

$strip\_tags \(bool\) \(Optional\) Removes potentially dangerous HTML tags

$strip\_scripts \(bool\) \(Optional\) Removes &lt;script&gt; tags

### Return <a id="return"></a>

\(string\) Sanitized and safe string

### **Example**

```php
$text = 'Text <a href="javascript:function()">click</a> <i onload=xss></i> <script>javascript code</script>';
echo descript($text);
// Text &lt;a href=&quot;nojavascript...function()&quot;&gt;click&lt;/a&gt; &lt;i &gt;&gt;&lt;/i&gt; javascript code
```

