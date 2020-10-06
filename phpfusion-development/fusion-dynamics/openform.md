---
description: >-
  The function should be able used to replace conventional <form> tags to
  provide an enhanced feature to your application.
---

# openform\(\)

Versions: `9`

openform\( string $form\_name, string $method \[, string $action\_url, array $options \] \) : string

### Parameters <a id="parameters"></a>

$form\_name \(string\) \(Required\) Form ID.

$method \(string\) \(Required\) Possible value: post, get.

$action\_url \(string\) \(Optional\) Form current uri. Default value: FORM\_REQUEST

$options \(array\) \(Optional\) Default value: \[\]

{% tabs %}
{% tab title="Version 9" %}
| Name | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| form\_id | string | $form\_name |  |
| class | string | '' | CSS class properties. |
| enctype | bool | false | Set true for allowing multipart. |
| max\_tokens | int | $settings\['form\_tokens'\] |   |
| inline | bool | false | Set true for making form inline. |
| on\_submit | string | '' | Adds javascript function on form submit. |
| honeypot | bool | true | Enables honeypots to counter botting. |
{% endtab %}

{% tab title="Version 10" %}
In Version 10, the function is further extended to allow more enhanced options features to handle post and sanitization. This enhancement allows code to be more simplified and be more robust. 

{% hint style="warning" %}
Support feature is currently under development. 
{% endhint %}

| Name | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| post\_db | string |  | Set table to target. |
| post\_id\_col | string |  | Primary key column. |
| post\_id\_value | string |  | Primary value for primary key column. |
| post\_button | string |  | Post button name. Array or string supported. |
| post\_mode | string | save | Form action. Save, Update, Auto. |
| post\_success\_message | string |  | Set a system message for successful post. |
| post\_redirect\_url | string | FORM\_REQUEST | Redirect url for post. |
| post\_data | string |  | Callback data in the event. |
| no\_unique | bool | false | Set true if current table have no primary column. |
| post\_mapping | string |  | Specify which table and column relationships in an array format. |
| post\_function |  |  | Specify custom post functions. Can have multiple functions declared using array. |
| post\_debug | bool | false | Set true for debug mode. |
{% endtab %}
{% endtabs %}

### Return Values

\(string\)

### **Examples**

```php
echo openform('testform', 'post');
```

