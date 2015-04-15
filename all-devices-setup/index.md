---
group: web-dev-2
playlist: PLWjCJDeWfDdfU7nLY0WOFXq3Q7n5ZyEuZ
download: https://github.com/acgd-learn-the-web/all-devices-setup-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/all-devices-setup-code
---

Since we are making websites designed for all devices, we want to setup our HTML and CSS to show it.

There are a couple `<meta>` tags and a little bit of CSS to make all devices recognize your website supports the device, whatever it is.

---

## HTML

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

- **handheldfriendly** & **mobileoptimized** are for older devices
	- The `240` states that our website is formatted for a minimum width of 240 pixels
- **viewport** is for newer smartphones. There are three arguments to specify:
	- `width=device-width`—our website is formatted for the prime width of the device
	- `initial-scale=1`—our website shouldn’t be zoomed in or out by default

---

## CSS

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

The `@viewport` rule is a replacement for the viewport meta tag but is new and only supported by a few browsers.
Since we’re future thinking designers we want to put it in.
**It’s probably best to put this at the very top of your CSS file.**

The `box-sizing` section changes the box model in CSS so that padding is inside the width—for many people this newer box model is easier to understand and use.

Since we are optimizing our sites for small screens, we want to stop small-screen browsers from inflating our font-size in an attempt to make our sites more readable.
That’s what the `text-size-adjust` property does.

---

## Video list

1. [All devices setup](https://www.youtube.com/watch?v=nbqnFZFQxd0&list=PLWjCJDeWfDdfU7nLY0WOFXq3Q7n5ZyEuZ&index=1)

## Supplemental links

- [Mozilla Docs: Meta Viewport Tag](https://developer.mozilla.org/en/Mobile/Viewport_meta_tag/)
- [Opera Dev: An Introduction to Meta Viewport and CSS Viewport](http://dev.opera.com/articles/view/an-introduction-to-meta-viewport-and-viewport/)
- [Learn the Mobile Web: Mobile Meta Tags](http://learnthemobileweb.com/blog/2009/07/mobile-meta-tags/)
