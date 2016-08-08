---
playlist: PLWjCJDeWfDdfU7nLY0WOFXq3Q7n5ZyEuZ
download: https://github.com/acgd-learn-the-web/all-devices-setup-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/all-devices-setup-code
---

Since we are making websites designed for all devices, we want to setup our HTML and CSS to show it.

The Open Web is about inclusion: about making our websites work for anybody in the world. There are just a couple `<meta>` tags and a little bit of CSS to make all devices recognize that our website supports any device.

---

## HTML

First, we need to set up our HTML so it works best in all devices.

HTML is fully cross platform, most elements will work in all browsers, but they may not be displayed exactly the same.

*And remember that if our CSS doesn’t load, our HTML is still fully functional, readable, and understandable.*

```html
⋮
<head>
  ⋮
  <meta name="handheldfriendly" content="true">
  <meta name="mobileoptimized" content="240">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  ⋮
</head>
⋮
```

- **handheldfriendly** & **mobileoptimized** are for older devices.
  - The `240` states that our website is formatted for a minimum width of 240 pixels.
- **viewport** is for newer smartphones. There are three arguments to specify:
  - `width=device-width`—our website is formatted for the width of the device.
  - `initial-scale=1`—our website shouldn’t be zoomed in or out by default.

In newer versions of Safari iOS you may also need to include `shrink-to-fit=no`, so the `viewport` meta tag would look like this:

```html
<meta name="viewport" content="width=device-width,initial-scale=1,shrink-to-fit=no">
```

This prevents Safari from scaling if there are elements that exceed the width of the device.

**Links**

- [Shrink to Fit](http://jsbin.com/fubunucopi/4/edit?html,output)

---

## CSS

In our CSS we adjust a few more things to help us create cross-device websites a little more consistently and easily.

```css
@-moz-viewport { width: device-width; scale: 1; }
@-ms-viewport { width: device-width; scale: 1; }
@-o-viewport { width: device-width; scale: 1; }
@-webkit-viewport { width: device-width; scale: 1; }
@viewport { width: device-width; scale: 1; }

html {
  box-sizing: border-box;

  -moz-text-size-adjust: 100%;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  text-size-adjust: 100%;
}

*, *::before, *::after {
  box-sizing: inherit;
}

⋮
```

The `@viewport` rule is a replacement for the viewport meta tag but is new and only supported by a few browsers. Since we’re future thinking designers we want to put it in. **It’s probably best to put this at the very top of your CSS file.**

The `box-sizing` section changes the box model in CSS so that padding is inside the width—for many people this newer box model is easier to understand and use.

Since we are optimizing our sites for small screens, we want to stop small-screen browsers from inflating our font-size in an attempt to make our sites more readable. That’s what the `text-size-adjust` property does.

---

## Resets & normalizers

In the past it was common practice to use a CSS reset. The reset would remove all the default styling provided by the browser so that it wouldn’t interfere with your development.

There’s been lots of research and studies done on CSS resets and they’ve fallen out of practice for a few reasons, performance being one of the main reasons. My belief is that CSS resets aren’t necessary because they force you to fight against the browser, re-styling everything, instead of just embracing the medium.

One piece of code that has become popular, replacing resets, is normalizers. Normalizers work differently: instead of removing all the default styles, forcing you to start fresh, they just make all the default styles consistent across browsers.

The most common normalizer is [Normalize.css](https://necolas.github.io/normalize.css/). I often include `normalize.css` in my websites, or a modified version of it, to help with consistency across browsers.

**Links**

- **[Normalize.css](https://necolas.github.io/normalize.css/)**

---

## Video list

1. [All devices setup](https://www.youtube.com/watch?v=nbqnFZFQxd0&list=PLWjCJDeWfDdfU7nLY0WOFXq3Q7n5ZyEuZ&index=1)

## Supplemental links

- [Mozilla Docs: Meta Viewport Tag](https://developer.mozilla.org/en/Mobile/Viewport_meta_tag/)
- [Opera Dev: An Introduction to Meta Viewport and CSS Viewport](http://dev.opera.com/articles/view/an-introduction-to-meta-viewport-and-viewport/)
- [Learn the Mobile Web: Mobile Meta Tags](http://learnthemobileweb.com/blog/2009/07/mobile-meta-tags/)
