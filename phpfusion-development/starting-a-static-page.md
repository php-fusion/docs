---
description: Learn how to code and work with PHPFusion CMS
---

# Starting a static page

## Preface

PHPFusion CMS is a barebone CMS at a first glance that provides you with a CMS like functionality surrounding your work. When working on a custom project, you basically start at scratch. When you start with a new file, that file is also your current browser URI. 

As you go along developing on your project and as you start to add files, there are a huge library available to assist you to achieve what you intend to do, and this documentation intends to describe them for you.

As the pioneer in lightweight CMS since 2003, PHPFusion has move beyond many extensions and redevelopment. However, we have kept its structure as simple as to make it very possible to you to focus on your project scope.

### **Getting started with your first static page**

**demo.php**

```php
<?php
require_once __DIR__."/maincore.php";
require_once THEMES."templates/header.php";

echo "My first line of code";

require_once THEMES."templates/footer.php";

```

{% hint style="info" %}
Browsing to `http://{your-server-url.com}/demo.php` on your server will reveal the demo page.
{% endhint %}

