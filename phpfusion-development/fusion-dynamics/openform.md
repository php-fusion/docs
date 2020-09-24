# openform\(\)

The function should be able used to replace conventional &lt;form&gt; tags to provide an enhanced feature to your application.

#### $options

{% tabs %}
{% tab title="Version 9" %}
| Parameter | Description |
| :--- | :--- |
| form\_id | default to $form\_name |
| class | CSS class properties. |
| enctype | Default FALSE. Set TRUE for allowing multipart. |
| max\_tokens | Default system settings form tokens.  |
| inline | Default FALSE. Set TRUE for making form field inline. |
| on\_submit | Adds javascript function on form submit. |
| honeypot | Default TRUE. Enables honeypots to counter botting. |
|  |  |
{% endtab %}

{% tab title="Version 10" %}
In Version 10, this function is further extended to allow more enhanced features to handle post and sanitization. This enhancement allows code to be more simplified and be more robust. 

{% hint style="warning" %}
Support feature is currently under development. 
{% endhint %}

| Parameter | Description |
| :--- | :--- |
| post\_db | Set table to target |
| post\_id\_col | Primary key column |
| post\_id\_value | Primary value for primary key column |
| post\_button | Post button name. Array or string supported. |
| post\_mode | Default "save". Form action. Save, Update, Auto |
| post\_success\_message | Set a system message for successful post. |
| post\_redirect\_url | Default FORM\_REQUEST. Redirect url for post |
| post\_data | Callback data in the event. |
| no\_unique | Default FALSE. Set TRUE if current table have no Primary column |
| post\_mapping | Specify which table and column relationships in an array format. |
| post\_function | Specify custom post functions. Can have multiple functions declared using array. |
| post\_debug | Default FALSE. Set true for debug mode. |
{% endtab %}
{% endtabs %}





