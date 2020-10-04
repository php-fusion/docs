---
description: Displays Site Links navigation bar.
---

# showsublinks\(\)

Versions: `9`

showsublinks\( \[ string $sep, string $class, array $options \] \) : string

### Parameters <a id="parameters"></a>

$sep \(string\) \(Optional\) Separator between links. Default value: ''

$class \(string\) \(Optional\) CSS class of the navbar. Default value: navbar-default

$options \(array\) \(Optional\) Default value: \[\]

| Name | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| id | string | DefaultMenu | ID of the menu. |
| container | bool | false | Show menu in &lt;div class="container"&gt;..&lt;/div&gt;.  |
| container\_fluid | bool | false | Show menu in &lt;div class="container-fluid"&gt;..&lt;/div&gt;.  |
| responsive | bool | true | Disable responsiveness. |
| navbar\_class | string | navbar-default | Already pre filled with value from $class. |
| nav\_class | string | nav navbar-nav primary | &lt;ul&gt; CSS class. |
| additional\_nav\_class | string | '' | CSS class of the secondary &lt;ul&gt; |
| item\_class | string | '' | &lt;li&gt; CSS class. |
| locale | array | \[\] | Additional locales. |
| separator | string | '' | Already pre filled with value from $sep. |
| links\_per\_page | int | null | Links per page. |
| grouping | bool | false | It works together with links\_per\_page. If you set links\_per\_page = 3, other links will be grouped under Show More dropdown. |
| show\_banner | bool | false |  |
| show\_header | string\|bool | false | Custom header. |
| custom\_header | string | '' |  |
| language\_switcher | bool | false | Language switcher. |
| searchbar | bool | false | Search bar. |
| search\_icon | string | fa fa-search | Search button icon. |
| searchbar\_btn\_class | string | btn-primary | Search button class. |
| caret\_icon | string | caret | Cater icon. |
| link\_position | array | \[2, 3\] |  |
| html\_pre\_content | string | '' |  |
| html\_content | string | '' |  |
| html\_post\_content | string | '' |  |

### Return Values

\(string\)

### **Examples**

```php
echo showsublinks();
```

