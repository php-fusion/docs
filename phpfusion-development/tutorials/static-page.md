---
description: Learn how to create a static page.
---

# Static page

**page\_name.php**

```php
<?php
require_once __DIR__.'/maincore.php';
require_once THEMES.'templates/header.php';

// Content goes here

require_once THEMES.'templates/footer.php';
```

{% hint style="info" %}
Browsing to http://example.com/**page\_name.php** on your server will reveal the page.
{% endhint %}

