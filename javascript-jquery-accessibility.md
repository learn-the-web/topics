---
title: "JavaScript, jQuery & accessibility"
tags: "javascript jquery animations events common components tabs toggle panels buttons lightbox accessibility focus keyboard wai aria"
desc: "Looking at common JavaScript patterns & components and how we can make them more accessible."
playlist: javascript-jquery-accessibility
download: https://github.com/learn-the-web/javascript-jquery-accessibility-code/archive/master.zip
github: https://github.com/learn-the-web/javascript-jquery-accessibility-code
---

JavaScript isn’t inherently inaccessible, but without a little bit of care the code we write can disrupt accessibility features built into the browser.

---

## JavaScript isn’t inaccessible

Adding JavaScript code to your website doesn’t make the website inaccessible, but the code you write can make it inaccessible.

Browsers have lots of accessibility tools built into them, and since JavaScript gives us so much control we can interfere with those tools.

When we code controls with JavaScript that aren’t built into the browser, like tabs and sliders, we just need to be careful to present the correct semantics and accessibility features to the user: feedback, keyboard controls, etc.

### Proper semantics

Proper semantics are important for writing JavaScript because those elements have accessibility features built into them.

- If you’re creating a clickable button, that requires JavaScript to function use a `<button>` tag: the button tag announces itself as a button, has keyboard controls, and more.
- If you’re creating a feature that refers to a resource on the current page or another page, use an `<a>` tag: it has keyboard controls; and if the JavaScript fails to execute, the link will still do its default action.
- Don’t add click events to generic elements like a `<div>`: you technically can make a `<div>` clickable, but it doesn’t have any accessibility features like keyboard focus, or indications that it’s clickable in the accessibility tools.
  If you really must use a generic element add the appropriate ARIA properties like `role="button"` and make sure to code all the keyboard access features too.
- Use the browser’s default controls first: if it works like a checkbox, use a checkbox; if it works similar to the `<details>` element, use that instead.

### Progressive enhancement

Progressive enhancement is the idea that we should build our websites with the understanding that everybody’s situation is different: they may have an older browser, they may have JavaScript disabled, they may have a poor Internet connection. Each of these concerns may cause a problem in our website.

*So don’t rely on JavaScript working. Built your website first in a simple manner and build JavaScript on top.*

**[☛ See the tutorial on progressive enhancement.](/topics/progressive-enhancement/)**

---

## ARIA to add extra semantics

Always first try to use the appropriate semantics for the element, but if you cannot, ARIA can be used to supplement the accessibility features.

### Accessible labels

As an example, when creating close buttons on elements, maybe lightboxes or panels, we need to make sure they’re accessible.

1. Make sure to use `<button>` tag.
2. Put proper words inside the button, like `<button>Close</button>`.

*But, if it’s not possible to put a real word in the close button, then `aria-label` can be used as a supplement.*

The final solution may look something like this:

```html
<button aria-label="Close lightbox">×</button>
```

### Accessible toggle panels

Making toggle panels is JavaScript in fairly simple, [you can see the toggle panel code here](/topics/javascript-jquery-components/#toggle-panels).

But we still need to make them a little more accessible, we need to adjust the HTML a little by adding some ARIA attributes.

```html
<button class="btn" aria-expanded="false" aria-controls="panel-1">Toggle</button>

<div class="panel" id="panel-1" aria-hidden="true">
  <h1>Panel!</h1>
</div>
```

- `aria-expanded` — defines whether the panel is currently open or closed.
- `aria-controls` — points to the ID of the `<div>` that this button changes.
- `aria-hidden` — defines that the content inside this element shouldn’t be accessible to tools at this point.

Then, we need to make some slight adjustments to our JavaScript to change those attributes when the button is clicked:

```js
var $btn = $('.btn');
var $panel = $('.panel');

$btn.on('click', function () {
  $panel.toggleClass('js-panel-open');

  // See whether the panel is open or closed
  if ($btn.attr('aria-expanded') == 'false') {
    // It’s currently closed, so open it
    $btn.attr('aria-expanded', true);
    $panel.attr('aria-hidden', false);
  } else {
    // It’s currently open, so close it
    $btn.attr('aria-expanded', false);
    $panel.attr('aria-hidden', true);
  }
});
```

With these few adjustments to our code the toggle panels are now much more accessible, with the tools announcing the state of the panel, and hiding and showing the content from the accessibility tools when appropriate.

[☛ With a little progressive enhancement this code can be even more open web friendly.](/topics/progressive-enhancement/)

### Accessible tabs

Tabs are a very common control that developers build on websites. [You can see the tab tutorial here.](/topics/javascript-jquery-components/#tabs)

For the HTML we’ll start by adding some ARIA attributes:

```html
<ul class="tabs" role="tablist">
  <li role="presentation"><a href="#tab-1" role="tab" aria-controls="tab-1" aria-selected="true">Tab 1</a></li>
  <li role="presentation"><a href="#tab-2" role="tab" aria-controls="tab-2">Tab 2</a></li>
  <li role="presentation"><a href="#tab-3" role="tab" aria-controls="tab-3">Tab 3</a></li>
</ul>

<div class="tab-panels">
  <div class="panel" id="tab-1" role="tabpanel" aria-hidden="false">…</div>
  <div class="panel" id="tab-2" role="tabpanel" aria-hidden="true">…</div>
  <div class="panel" id="tab-3" role="tabpanel" aria-hidden="true">…</div>
</div>
```

There’s quite a bunch extra in the code above, here’s what we did:

- `role="tablist"` — tells the browser that this isn’t an ordinary list, but instead a list of tabs.
- `role="presentation"` — reminds the user that these aren’t list items, because they’re part of the tab list.
- `role="tab"` — tells the browser that this isn’t a link anymore, but instead a tab.
- `aria-controls` — connects the tab link to the `<div>` using its ID.
- `aria-selected` — defines whether the tab is the currently visible one or not; you could use this to style the tab instead of a class.
- `role="tabpanel"` — tells the browser that this isn’t just a `<div>` but a piece of tabbed content.
- `aria-hidden` — defines whether the tab is currently visible or not; you could use this to style the tab instead of the `hidden` attribute.

Now with the ARIA attributes in place we need to adjust our JavaScript a little bit.

```js
var $tabs = $('.tabs');
var $panels = $('.panel');

$tabs.on('click', 'a', function (e) {
  e.preventDefault();
  var id = $(this).attr('href');

  // Find the currently visible tab and panel and hide them
  $panels.filter('[aria-hidden="false"]').attr('aria-hidden', true);
  $tabs.find('[aria-selected="true"]').attr('aria-selected', false);

  // Set the new tab and panel to be visible
  $(this).attr('aria-selected', true);
  $(id).attr('aria-hidden', false);
});
```

*Instead of using the `.js-current` class and the `hidden` attribute in CSS to style the elements use the `aria-selected` and `aria-hidden` attributes.*

[☛ With a little progressive enhancement these tabs can be even more open web friendly.](/topics/progressive-enhancement/)

#### Keyboard controls for tabs

All the above changes work fairly well, but there’s lots more we can do to make the tabs more keyboard accessible.

- We can take control of the `tab` key to allow our users simpler navigation:
  1. The first `tab` will enter the controls.
  2. The second `tab` will leave the controls and enter the content instead of going to the next tab control.
- We can add arrow key support to the controls:
  1. Our user presses `tab` to get into the controls.
  2. Using the `left` and `right` arrow keys they can switch tabs.
  3. Pressing `tab` again will focus the content of the visible tab.

[☛ Browse the accessible tab code to see the result.](https://github.com/learn-the-web/javascript-jquery-accessibility-code)

**Links**

- **[Practical ARIA examples](http://heydonworks.com/practical_aria_examples/)**

---

## Video list

1. [JavaScript + jQuery accessibility: Proper semantics](https://videos.learntheweb.courses/playlists/javascript-jquery-accessibility/#1-semantics)
2. [JavaScript + jQuery accessibility: Proper labels](https://videos.learntheweb.courses/playlists/javascript-jquery-accessibility/#2-aria-label)
3. [JavaScript + jQuery accessibility: Making toggle panels](https://videos.learntheweb.courses/playlists/javascript-jquery-accessibility/#3-toggle-panels)
4. [JavaScript + jQuery accessibility: Making tabs](https://videos.learntheweb.courses/playlists/javascript-jquery-accessibility/#4-tabs)
5. [JavaScript + jQuery accessibility: Tab keyboard controls](https://videos.learntheweb.courses/playlists/javascript-jquery-accessibility/#5-tab-keyboard)

## Supplemental links

- **[Web Experience Toolkit](https://wet-boew.github.io/wet-boew/index-en.html)**
- [aria-live: the good, the bad and the ugly](http://www.slideshare.net/maxdesign/arialive-the-good-the-bad-and-the-ugly)
