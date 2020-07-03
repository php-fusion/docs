---
description: format_word - returns a grammatical number word
---

# format\_word

`(Version 9)` `(Version 10)`

## Description

> format\_word \( int`$number` , string`$nouns` \[, array `$options` \] \) : string

**format\_word\(\)** returns a grammatical number word string from the $noun used as arguments for the callback. 

#### **Parameters**

`number`

A number

`nouns`

A string consisting of singular and plural delimited by a **`|`** symbol.

#### Return Values

Return a string of words with a correct grammatical word.  

#### $options - Parameters

<table>
  <thead>
    <tr>
      <th style="text-align:left">Key</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Default Values</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">add_count</td>
      <td style="text-align:left">show integer</td>
      <td style="text-align:left">true</td>
    </tr>
    <tr>
      <td style="text-align:left">html</td>
      <td style="text-align:left">encase result with html_template, <code>{%count%}</code>  <code>{%result%}</code> tags
        are used for placeholders for result replacements.</td>
      <td style="text-align:left">IMAGES</td>
    </tr>
    <tr>
      <td style="text-align:left">html_template</td>
      <td style="text-align:left">HTML template to be used for output</td>
      <td style="text-align:left">
        <p>&lt;/span&gt;</p>
        <p>&lt;/span&gt;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">language</td>
      <td style="text-align:left">current display language</td>
      <td style="text-align:left"><b><code>LANGUAGE</code></b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">format_num</td>
      <td style="text-align:left">executes <b><code>format_num</code></b> before parsing results</td>
      <td style="text-align:left">TRUE</td>
    </tr>
  </tbody>
</table>

#### Examples \#1 - counting a noun

```php
$array = array(
"Apple", "Orange"
);
$count = count($array);
echo format_word($count, "fruit|fruits"); // Returns "2 fruits"
```

#### Example \#2 - generate a sentence dynamically

```php
$array = array(
"Sam", "Peter", "Mary"
);
$count = count($array);
echo format_sentence($array)." ".format_word($count, "is|are")." going to the party.";
```

