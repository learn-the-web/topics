---
title: "Before & after pseudo elements"
tags: "before after pseudo elements content hidden bullets quotations marks clearfix border box "
desc: "Understanding the hidden before and after pseudo elements, how to style them, and what they’re helpful for."
playlist: PLWjCJDeWfDddMjtm6wwgpUMYZZC0I9xZz
download: https://github.com/ltw-learn-the-web/before-after-code/archive/master.zip
github: https://github.com/ltw-learn-the-web/before-after-code
---

Every HTML element in the code is actually composed of 3 separate elements—two of them are just hidden by default.

---

## The hidden elements

Every element has two hidden elements, called pseudo elements, that can be styled and used to create interesting effects.

The elements are named `::before` and `::after` because of where they’re positioned by default.

Just like every HTML element, they aren’t visible because they don’t have any content inside them.

### Adding content

To add content inside the pseudo-element use the `content` property.

```css
div::before {
	content: " "; /* A space */
}

.box::after {
	content: "Dino"; /* The word "Dino" */
}
```

### Styling before & after

After adding content to the pseudo-elements they are visible. We can now treat the elements like any other HTML element and style them with any property we want.

```css
.box::after {
	content: "Dino";
	display: inline-block;
	padding: 0.5em;
	background-color: darkgreen;
	border-radius: 8px;
}
```

### Positioning before & after

We can even us the standard positioning, floating, etc. to move them around.

*They are technically **inside** their parent element, so `position: relative` and `position: absolute` rules apply.*

```html
<div class="box">…</div>
```

```css
.box {
	position: relative;
}

.box::before {
	content: "Dino";
	background-color: darkgreen;
	position: absolute;
	top: -1.5rem;
	left: -5em;
}
```

---

## Where have I seen this before?

You may remember seeing us use `::before` and `::after` in a few other places previously:

1. [When setting up our website to use border-box](../box-model#adjusting-layout-math-with-border-box)
2. [As a clearfix when floating elements](../float-clear#clearfix-class)

---

## Making custom bullets

The default bullets associated with unordered lists in HTML are hard to style. With `::before` and `::after` we can replace them with our own bullets and get more control over their styling.

```html
<ul class="dinos">
	<li>Apatosaurus</li>
	<li>Stegosaurus</li>
	<li>Triceratops</li>
</ul>
```

With a `<ul>` like above, we first need to remove the default bullets before we add our own.

```css
.dinos {
	list-style-type: none;
	padding: 0; /* Maybe remove the padding too */
}

.dinos li::before {
	content: "·"; /* A middle dot (a small bullet) */
	display: inline-block;
	margin-right: 0.3em;
	color: #ccc;
}
```

By targeting the `<li>` elements we are putting a custom bullet in front of each of them. With `::before` we can then assign any style we want to the bullets to differentiate them from the text.

---

## Fancy quotation marks

When making pull quotes on our website it seems unnecessary to have to create an element with a single quotation mark inside it for styling. Before and after come in really handing for this situation.

```html
<blockquote>
  <p>In every island of the Aegean Sea are found abundant traces of a vast prehistoric empire.</p>
  <footer>— <cite>James Theodore Bent</cite></footer>
</blockquote>
```

We don’t need to specify the quote marks in the `<blockquote>` because that element already defines the text as a quote.

Then, in our CSS we just create new quote marks and position them into place.

```css
blockquote {
  position: relative;
}

blockquote::before {
  content: "“"; /* Real curly quotes */
  font-size: 3rem;
  color: hotpink;
  position: absolute;
  left: -0.6em;
  top: 0;
}

blockquote::after {
  content: "”"; /* Real curly quotes */
  font-size: 3rem;
  color: hotpink;
  position: absolute;
  right: -0.6em;
  bottom: 0;
}
```

---

## Other ideas

- You can use `background-image` to insert images into before and after
- Check out CSS counters to generate numbers
- Use before and after to make a page curl effect
- Grab content from attributes using the `attr()` function

**Links**

- [MDN: CSS counters](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Counters)

---

## Video list

1. [Before & after: the hidden elements](https://www.youtube.com/watch?v=hv2j8NZRCzo&index=1&list=PLWjCJDeWfDddMjtm6wwgpUMYZZC0I9xZz)
2. [Before & after: custom bullets](https://www.youtube.com/watch?v=BmMj3ss2tY8&index=2&list=PLWjCJDeWfDddMjtm6wwgpUMYZZC0I9xZz)
3. [Before & after: quotation marks](https://www.youtube.com/watch?v=H47TgxyBnAU&index=3&list=PLWjCJDeWfDddMjtm6wwgpUMYZZC0I9xZz)
4. [Before & after: decorations](https://www.youtube.com/watch?v=WiaIBC7xszw&index=4&list=PLWjCJDeWfDddMjtm6wwgpUMYZZC0I9xZz)

## Supplemental links

- [MDN: ::before](https://developer.mozilla.org/en-US/docs/Web/CSS/::before)
- [MDN: ::after](https://developer.mozilla.org/en-US/docs/Web/CSS/::after)
- [CSS-Tricks: ::after/::before](https://css-tricks.com/almanac/selectors/a/after-and-before/)
- [Can I use: CSS Generated content for pseudo-elements](http://caniuse.com/#feat=css-gencontent)
- [Smashing Magazine: Learning To Use The :before And :after Pseudo-Elements In CSS](http://www.smashingmagazine.com/2011/07/13/learning-to-use-the-before-and-after-pseudo-elements-in-css/)
- [Codrops: ::before](http://tympanus.net/codrops/css_reference/before/)
- [Codrops: ::after](http://tympanus.net/codrops/css_reference/after/)
