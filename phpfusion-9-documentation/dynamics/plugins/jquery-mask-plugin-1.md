---
description: A jQuery Plugin to make masks on form fields and HTML elements.
---

# jQuery Mask Plugin

### Features

* Lightweight \(~2kb minified, ~1kb gziped\).
* Built-in support for dynamically added elements.
* Masks on any HTML element \(no need to server-side mask anymore!\)!
* HTML notation support \(data-mask, data-mask-recursive, data-mask-clearifnotmatch\).
* String/Numeric/Alpha/Mixed masks.
* Reverse mask support for masks on numeric fields.
* Sanitization.
* Optional digits.
* Recursive Digits.
* Fallback Digits.
* Advanced mask initialization.
* Advanced Callbacks.
* On-the-fly mask change.
* Mask removal.
* Full customization.
* Compatibility with React/UMD/Zepto.js/Angular.JS.
* HTML5 placeholder support.
* Clear the field if it not matches support.

#### Basic Usage <a id="basic-usage"></a>

```text
$(document).ready(function(){
  $('.date').mask('00/00/0000');
  $('.time').mask('00:00:00');
  $('.date_time').mask('00/00/0000 00:00:00');
  $('.cep').mask('00000-000');
  $('.phone').mask('0000-0000');
  $('.phone_with_ddd').mask('(00) 0000-0000');
  $('.phone_us').mask('(000) 000-0000');
  $('.mixed').mask('AAA 000-S0S');
  $('.cpf').mask('000.000.000-00', {reverse: true});
  $('.cnpj').mask('00.000.000/0000-00', {reverse: true});
  $('.money').mask('000.000.000.000.000,00', {reverse: true});
  $('.money2').mask("#.##0,00", {reverse: true});
  $('.ip_address').mask('0ZZ.0ZZ.0ZZ.0ZZ', {
    translation: {
      'Z': {
        pattern: /[0-9]/, optional: true
      }
    }
  });
  $('.ip_address').mask('099.099.099.099');
  $('.percent').mask('##0,00%', {reverse: true});
  $('.clear-if-not-match').mask("00/00/0000", {clearIfNotMatch: true});
  $('.placeholder').mask("00/00/0000", {placeholder: "__/__/____"});
  $('.fallback').mask("00r00r0000", {
      translation: {
        'r': {
          pattern: /[\/]/,
          fallback: '/'
        },
        placeholder: "__/__/____"
      }
    });
  $('.selectonfocus').mask("00/00/0000", {selectOnFocus: true});
});
```

#### Callback examples <a id="callback-examples"></a>

```text
var options =  {
  onComplete: function(cep) {
    alert('CEP Completed!:' + cep);
  },
  onKeyPress: function(cep, event, currentField, options){
    console.log('A key was pressed!:', cep, ' event: ', event,
                'currentField: ', currentField, ' options: ', options);
  },
  onChange: function(cep){
    console.log('cep changed! ', cep);
  },
  onInvalid: function(val, e, f, invalid, options){
    var error = invalid[0];
    console.log ("Digit: ", error.v, " is invalid for the position: ", error.p, ". We expect something like: ", error.e);
  }
};

$('.cep_with_callback').mask('00000-000', options);
```

#### On-the-fly mask change <a id="on-the-fly-mask-changes"></a>

```text
var options =  {
  onKeyPress: function(cep, e, field, options) {
    var masks = ['00000-000', '0-00-00-00'];
    var mask = (cep.length>7) ? masks[1] : masks[0];
    $('.crazy_cep').mask(mask, options);
}};

$('.crazy_cep').mask('00000-000', options);
```

#### Mask as a function <a id="mask-as-a-function"></a>

```text
var SPMaskBehavior = function (val) {
  return val.replace(/\D/g, '').length === 11 ? '(00) 00000-0000' : '(00) 0000-00009';
},
spOptions = {
  onKeyPress: function(val, e, field, options) {
      field.mask(SPMaskBehavior.apply({}, arguments), options);
    }
};

$('.sp_celphones').mask(SPMaskBehavior, spOptions);
```

#### Using HTML notation examples <a id="using-html-notation-examples"></a>

To get your mask applied with the data-mask attribute just use it as the same way you use with the $.mask function.

```text
<input type="text" name="field-name" data-mask="00/00/0000" />
```

Activating a reversible mask

```text
<input type="text" name="field-name" data-mask="00/00/0000" data-mask-reverse="true" />
```

Using clearIfNotMatch option

```text
<input type="text" name="field-name" data-mask="00/00/0000" data-mask-clearifnotmatch="true" />
```

Using selectOnFocus option

```text
<input type="text" name="field-name" data-mask="00/00/0000" data-mask-selectonfocus="true" />
```

#### Translation <a id="translation"></a>

Teach to jQuery Mask Plugin how to apply your mask:

```text
// now the digit 0 on your mask pattern will be interpreted
// as valid characters like 0,1,2,3,4,5,6,7,8,9 and *
$('.your-field').mask('00/00/0000', {'translation': {0: {pattern: /[0-9*]/}}});
```

By default, jQuery Mask Plugin only reconizes the logical digit A \(Numbers and Letters\) and S \(A-Za-z\) but you can extend or modify this behaviour by telling to jQuery Mask Plugin how to interpret those logical digits.

```text
$('.your-field').mask('AA/SS/YYYY', {'translation': {
    A: {pattern: /[A-Za-z0-9]/},
    S: {pattern: /[A-Za-z]/},
    Y: {pattern: /[0-9]/}
  }
});
```

Now jQuery Mask Plugin knows the logic digit Y and you can create your own pattern.

**Optional digits**

You can also tell to jQuery Mask which digit is optional, to create a IP mask for example:

```text
// way 1
$('.ip_address').mask('099.099.099.099');
// way 2
$('.ip_address').mask('0ZZ.0ZZ.0ZZ.0ZZ', {translation:  {'Z': {pattern: /[0-9]/, optional: true}}});
```

Now, all Z digits in your masks is optional.

**Recursive digits**

With jQuery Mask Plugin you can also define recursive patterns inside your mask:

```text
$('.money_example').mask('#.##0,00', {reverse: true});
```

With example above the mask will be placed from the right to the left \(that's why reverse:true is defined\). As soon as you start typing, a "0,00" will be applied followed by repeating recursively the following pattern "\#.\#\#". The result could be something like: 1.234.567,890.

You can also use that kind of feature to define what kind of data could be typed inside of a field:

```text
$('.example').mask('0#');
```

Now only numbers will be allowed inside your form field.

**Fallback digits**

When a user types a invalid char for the current position the plugin will replace it by its fallback instead of erasing them.

```text
$('.money_example').mask('#.##0,00', { reverse: true });
```

#### Removing the mask <a id="removing-the-mask"></a>

```text
$('.date').unmask();
```

#### Getting the unmasked typed value <a id="getting-the-unmasked-typed-value"></a>

```text
$('.date').cleanVal();
```

#### Getting a masked value programmatically <a id="getting-a-masked-value-programmatically"></a>

```text
$('.date').masked('19840807');
```

### Customization

#### Field options <a id="field-options"></a>

```text
var custom_options = {
  byPassKeys: [8, 9, 37, 38, 39, 40],
  translation: {
    '0': {pattern: /\d/},
    '9': {pattern: /\d/, optional: true},
    '#': {pattern: /\d/, recursive: true},
    'A': {pattern: /[a-zA-Z0-9]/},
    'S': {pattern: /[a-zA-Z]/}
  };
};
```

**byPassKeys** list of keyboard's keyCode that you want to be ignored when it was pressed.  
**translation** object with all digits that should be interpreted as a special chars and its regex representation.

#### Public methods <a id="public-methods"></a>

```text
/**
Applies the mask to the matching selector elements.

@selector elements to be masked.
@mask should be a string or a function.
@options should be an object.
**/
$(selector).mask(mask [, options]);

/**
Seek and destroy.

@selector elements to be masked.
**/
$(selector).unmask();

/**
Gets the value of the field without the mask.

@selector elements to be masked.
**/
$(selector).cleanVal();

/**
Applies the mask to the matching selector elements.

@selector optional: elements to be masked. The default behaviour it's to lookup for all elements with data-mask attribute.
**/
$.applyDataMask([selector]);
```

#### Global options <a id="global-options"></a>

```text
/**
nonInput: elements we consider nonInput
dataMask: we mask data-mask elements by default
watchInputs: watch for dynamically added inputs by default
watchDataMask: by default we disabled the watcher for dynamically
added data-mask elements by default (performance reasons)
**/

$.jMaskGlobals = {
  maskElements: 'input,td,span,div',
  dataMaskAttr: '*[data-mask]',
  dataMask: true,
  watchInterval: 300,
  watchInputs: true,
  watchDataMask: false,
  byPassKeys: [9, 16, 17, 18, 36, 37, 38, 39, 40, 91],
  translation: {
    '0': {pattern: /\d/},
    '9': {pattern: /\d/, optional: true},
    '#': {pattern: /\d/, recursive: true},
    'A': {pattern: /[a-zA-Z0-9]/},
    'S': {pattern: /[a-zA-Z]/}
  }
};
```

#### Author Credits:

Source: [https://igorescobar.github.io/jQuery-Mask-Plugin/docs.html](https://igorescobar.github.io/jQuery-Mask-Plugin/docs.html)  
Created by Igor Escobar on 2012-03-10. Please report any bug at [http://blog.igorescobar.com](http://blog.igorescobar.com)



