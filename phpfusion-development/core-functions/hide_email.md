---
description: >-
  Hide email from robots that have JavaScript disabled, as it requires
  JavaScript to view email.
---

# hide\_email\(\)

Versions: `9`

hide\_email\( string $email \[, string $title, string $subject \] \)

### Parameters <a id="parameters"></a>

$email \(string\) \(Required\) The email you want to hide from robots.

$title \(string\) \(Optional\) The text of the link. Default value: ''

$subject \(string\) \(Optional\) A subject for a mail message if someone opens a link and it opens in the mail client. Default value: '''

### Return Values

\(string\) If browser has JavaScript enabled, email will be displayed correctly, otherwise it will be hidden and difficult for robot to decrypt.

### **Examples**

```php
echo hide_email('example@example.com');
// <a href="mailto:example@example.com">example@example.com</a>
```

