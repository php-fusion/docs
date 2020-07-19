---
description: Documentation for clipboard.js
---

# Clipboard.js

We're living a _declarative renaissance_, that's why we decided to take advantage of [HTML5 data attributes](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_data_attributes) for better usability.

#### Copy text from another element

A pretty common use case is to copy content from another element. You can do that by adding a `data-clipboard-target` attribute in your trigger element.

The value you include on this attribute needs to match another's element selector.

```text
<!-- Target -->
<input id="foo" value="https://github.com/zenorocha/clipboard.js.git">

<!-- Trigger -->
<button class="btn" data-clipboard-target="#foo">
    <img src="assets/clippy.svg" alt="Copy to clipboard">
</button>
```

#### Cut text from another element

Additionally, you can define a `data-clipboard-action` attribute to specify if you want to either `copy` or `cut` content.

If you omit this attribute, `copy` will be used by default.Cut to clipboard

```text
<!-- Target -->
<textarea id="bar">Mussum ipsum cacilds...</textarea>

<!-- Trigger -->
<button class="btn" data-clipboard-action="cut" data-clipboard-target="#bar">
    Cut to clipboard
</button>
```

As you may expect, the `cut` action only works on `<input>` or `<textarea>` elements.

#### Copy text from attribute

Truth is, you don't even need another element to copy its content from. You can just include a `data-clipboard-text` attribute in your trigger element.Copy to clipboard

```text
<!-- Trigger -->
<button class="btn" data-clipboard-text="Just because you can doesn't mean you should — clipboard.js">
    Copy to clipboard
</button>
```

## Events <a id="events"></a>

There are cases where you'd like to show some user feedback or capture what has been selected after a copy/cut operation.

That's why we fire custom events such as `success` and `error` for you to listen and implement your custom logic.

```text
var clipboard = new ClipboardJS('.btn');

clipboard.on('success', function(e) {
    console.info('Action:', e.action);
    console.info('Text:', e.text);
    console.info('Trigger:', e.trigger);

    e.clearSelection();
});

clipboard.on('error', function(e) {
    console.error('Action:', e.action);
    console.error('Trigger:', e.trigger);
});
```

For a live demonstration, just open your console :\)

## Tooltips <a id="tooltips"></a>

Each application has different design needs, that's why clipboard.js does not include any CSS or built-in tooltip solution.

The tooltips you see on this demo site were built using [GitHub's Primer](https://github.com/primer/primer-css/tree/master/modules/primer-tooltips). You may want to check that out if you're looking for a similar look and feel.

## Advanced Usage <a id="advanced-usage"></a>

If you don't want to modify your HTML, there's a pretty handy imperative API for you to use. All you need to do is declare a function, do your thing, and return a value.

For instance, if you want to dynamically set a `target`, you'll need to return a Node.

```text
new ClipboardJS('.btn', {
    target: function(trigger) {
        return trigger.nextElementSibling;
    }
});
```

If you want to dynamically set a `text`, you'll return a String.

```text
new ClipboardJS('.btn', {
    text: function(trigger) {
        return trigger.getAttribute('aria-label');
    }
});
```

For use in Bootstrap Modals or with any other library that changes the focus you'll want to set the focused element as the `container` value.

```text
new ClipboardJS('.btn', {
    container: document.getElementById('modal')
});
```

Also, if you are working with single page apps, you may want to manage the lifecycle of the DOM more precisely. Here's how you clean up the events and objects that we create.

```text
var clipboard = new ClipboardJS('.btn');
clipboard.destroy();
```

## Browser Support <a id="browser-support"></a>

This library relies on both [Selection](https://developer.mozilla.org/en-US/docs/Web/API/Selection) and [execCommand](https://developer.mozilla.org/en-US/docs/Web/API/Document/execCommand) APIs. The first one is [supported by all browsers](https://caniuse.com/#search=selection) while the second one is supported in the following browsers.

The good news is that clipboard.js gracefully degrades if you need to support older browsers. All you have to do is show a tooltip saying `Copied!` when `success` event is called and `Press Ctrl+C to copy` when `error` event is called because the text is already selected.

You can also check if clipboard.js is supported or not by running `ClipboardJS.isSupported()`, that way you can hide copy/cut buttons from the UI.

## Bonus <a id="bonus"></a>

A browser extension that adds a "copy to clipboard" button to every code block on _GitHub, MDN, Gist, StackOverflow, StackExchange, npm, and even Medium._

Install for [Chrome](https://chrome.google.com/webstore/detail/codecopy/fkbfebkcoelajmhanocgppanfoojcdmg) and [Firefox](https://addons.mozilla.org/en-US/firefox/addon/codecopy/).

