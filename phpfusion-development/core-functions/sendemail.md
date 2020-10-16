---
description: Send a mail to one or more email addresses.
---

# sendemail\(\)

Versions: `9`

sendemail\( string $toname, string $toemail, string $fromname, string $fromemail, string $subject, string $message \[, string $type, string $cc, string $bcc \] \) : bool

## Parameters <a id="parameters"></a>

$toname \(string\) \(Required\) The name of the receiver.

$toemail \(string\) \(Required\) The mail of the receiver.

$fromname \(string\) \(Required\) Sender's name.

$fromemail \(string\) \(Required\) Sender's email.

$subject \(string\) \(Required\) Email subject.

$message \(string\) \(Required\) Email message.

$type \(string\) \(Optional\) Text type. Possible value: text, html. Default value: text

$cc \(string\) \(Optional\) Carbon copy, whom do you want to send copies of this mail to. Default value: ''

$bcc \(string\) \(Optional\) Blind carbon copy, this receiver will not be able to see from whom this mail has been sent to others than the receiver. Default value: ''

## Return Values

\(bool\) True, if email was sent.

## Examples

```php
require_once INCLUDES.'sendmail_include.php';

$toname = 'Joe User';
$tomail = 'joe@example.net';
$fromname = 'Mailer';
$fromemail = 'from@example.com';
$subject = 'Here is the subject';
$message = 'This is the mail body.';
sendemail($toname, $tomail, $fromname, $fromemail, $subject, $message);
```

