---
title: "Flexbox"
tags: "css advanced layout flexbox align content justify vertical"
desc: "Learn how to use the flexbox layout system to create more advanced layouts with columns and alignments."
playlist: PLWjCJDeWfDdcae7fPzpUclV89TYFOa2Vq
download: https://github.com/acgd-learn-the-web/flexbox/archive/master.zip
github: https://github.com/acgd-learn-the-web/flexbox
cheatsheet: flexbox-cheat-sheet
extra_practice:
  week:
    title: "Web Dev 1, Week 09"
    url: "/courses/web-dev-1/week-09/"
  slides:
    - title: "Flexbox"
      url: "/courses/web-dev-1/flexbox"
  lessons:
    - title: "Flexing your muscles"
      url: "/courses/web-dev-1/flexing-your-muscles/"
  exercises:
    - title: "Header icons"
      url: "/courses/web-dev-1/week-08/#header-icons"
    - title: "Columns of cards"
      url: "/courses/web-dev-1/week-08/#columns-of-cards"
---

Flexbox allows you to control the flow of the elements on the page to make more complex layouts—like columns—and helps simply align things in two dimensions.

---

## It’s all about the children

Flexbox is one of many different ways to control the flow & layout of elements in your web design. It’s specifically good at distributing & aligning elements in a single dimension: generally for making elements fit beside each other on the same line. But can also work vertically.

Flexbox is different from many other CSS properties: instead of targeting an element and acting directly upon it, we target the parent element and that controls the layout of its children.

**We’re making a flex container and all the children of that container become flex items.**

```html
<section> <!-- ← Flexbox CSS goes here! -->
  <div></div>
  <div></div>
</section>
```

To make the two `<div>` tags above sit beside each other on the same line, we have to add only 1 line of CSS:

```css
section {
  display: flex;
}
```

![](display-flex.png)

**It’s extremely important that we add the CSS to the parent element, which then controls the layout of all the direct children within it.**

### Targets the direct children

We have to be very careful to group our elements, because flexbox works on children, so we can run into some weird situations.

```html
<section>
  <h2>Unicorns</h2>
  <p>Majestic, magical myths.</p>
  <h2>Narwhals</h2>
  <p>Noteworthy, nice normal.</p>
</section>
```

With HTML like the above, if we added `display: flex` to the parent (`<section>`) we’d essentially be trying to get all 4 of those elements on the same line. Because flexbox acts on the direct children—it’s trying to layout the `<h2>` & `<p>` tags directly.

But, most likely, what we’re trying to achieve is two columns, so we need to be careful to group the elements together:

```html
<section>
  <div>
    <h2>Unicorns</h2>
    <p>Majestic, magical myths.</p>
  </div>
  <div>
    <h2>Narwhals</h2>
    <p>Noteworthy, nice normal.</p>
  </div>
</section>
```

With the proper grouping, the `<div>` tags are now affected by `display: flex` and the `<h2>` & `<p>` tags are not turned into flex items.

### Boxes: block & inline

When you set an element to `display: flex` you’re setting two things specifically: how the box itself will act (outer display) & how its children will act (inner display).

By default all flex containers act like block-level elements. And their children act like flex-items, trying to fit on the same line.

This is what you are essentially defining:

```css
section {
  display: block flex;
}
```

- `block` — How the outside of the box will act, like setting `display: block`
- `flex` — How the inside of the box will act, as flex items

*I bet you didn’t realize you can define `display` for both the “outside” the box and the “inside” of the box!*

But sometimes, we do want our flexboxes to behave more like `inline-block` containers, so there’s alternative mode that looks like this:

```css
section {
  display: inline-flex;
}
```

Which will make the parent element behave like an inline-block element while still allowing the children to be flex items.

![](flex-block-inline.png)

*You could actually write that as `display: inline flex` but the browser support isn’t so great right now.*

**Links**

- [What Happens When You Create A Flexbox Flex Container?](https://www.smashingmagazine.com/2018/08/flexbox-display-flex-container/)

### Say goodbye to margin collapse

[We talked about margin collapse previously](/topics/box-model/#margin-collapsing): how two margins that touch each other vertically will collapse to the size of the biggest one.

Well, of course, flexbox acts differently. Instead of the margins collapsing into the largest of the two: **all margins are honoured.**

![](no-margin-collapse.png)

**Two margins that butt against each other will not collapse but push each other away.**

---

## Justification & alignment

Flexbox gives us lots of control over how the elements within the flex container are aligned & distributed. There are a few different properties that we can apply to get elements to arrange the way we want.

### Flex item widths

First, we can use the standard `width` on our flex items to control how much space they take up.

![](flex-width.png)

```css
section div {
  width: 50%;
}
```

There’s an alternative property, [flex-basis](https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis), that works very similarly to `width` in many situations but has some other interesting side effects.

### Justifying content

We can distribute the elements along the axis that the flex items are arranged using the `justify-content` property.

There are a few different ways to use `justify-content`:

- `flex-start` — the default position
- `flex-end` — the opposite location of `flex-start`
- `center` — move all the items into the center of the arrangement
- `space-between` — makes the elements touch the start & end edges of the flex container then evenly distributes the space between the elements.
- `space-around` — adds equal space on both sides of the elements to space them out, unfortunately this doubles the spaces in the center of the elements from what’s on the edges.

![](justify-content.png)

Using our HTML above, we could do:

```css
section {
  justify-content: space-between;
}
```

### Aligning content

Where the justification properties work in the main arrangement, the alignment properties work in the opposite orientation to the main arrangement.

That’s a complicated way to saying that we can arrange elements against each other—it’s specifically helpful if the flex items are different sizes.

There are a few different ways to use `align-items`:

- `flex-start` — the default position
- `flex-end` — the opposite location of `flex-start`
- `center` — align the items against their centres, adjusting for their different dimensions
- `stretch` — force the elements to be the same size

![](align-items.png)

Using the HTML above, we could do:

```css
section {
  align-items: center;
}
```

### Ordering content

We can even rearrange the elements inside the flex container using the `order` property. We can then have the HTML in a logical order in the code, but display it visually in a different order.

The `order` property accepts an integer: the numbered position you want the item to be located at. We can also use negative numbers, for instance, `-1` will move something to the start.

```css
section div:last-child {
  order: -1;
}
```

![](order.png)

---

## Vertically flexible & wrapping

So far we’ve concentrated on positioning flex items horizontally, but flexbox also works vertically. Vertical flex containers are helpful for distributing content equally.

It’s now important to learn about flexbox’s axes and how that affects `justify-content` and `align-items`.

- `justify-content` always works on the “main” axis, for `flex-direction: row`, that’s horizontal, but if we switch to a `column` orientation, now the flex direction switches.
- `align-items` is the opposite, working on the “cross” axis, for `row` that means vertically, but for `column` it switches to be horizontal.

![](flex-axes.png)

**Remember that `justify-content` works in the direction you are arranging the elements. And `align-items` is opposite that.**

So, if we want to align items in a vertical orientation we can add `flex-direction: column`:

```css
section {
  flex-direction: column;
}
```

### Reverse directions

There’s also the reverse direction, which works similar to order, but allows you to completely reorder the elements opposite to what their written in the code:

```css
section {
  flex-direction: row-reverse; /* or column-reverse */
}
```

### Wrapping flex items

When there isn’t enough space in the container we can also get flex items to wrap to the next line, similar to the browser’s standard flow works. Wrapping flex items isn’t terribly reliable but sometimes works the way you need it to.

![](flex-wrap.png)

```css
section {
  flex-wrap: wrap;
}
```

That brings us to another alignment property: `align-content`. `align-content` only works when the elements are wrapped within their flexbox container and allows you to align the whole grouping of those wrapped elements.

![](align-content.png)

```css
section {
  align-content: center;
}
```

If you can stick to flexbox working in only a single dimension, AKA not wrapping, you’ll probably have a better time creating the layouts but wrapping can work to your advantage sometimes—especially responsive websites.

---

## Flexbox navigation

Making a navigation bar using flexbox has completely identical HTML to any other kind of navigation—except flexbox will give us *much* more control of the alignment & distribution of the navigation items on our page.

So, let’s start with that basic HTML:

```html
<header>
  <nav>
    <ul>
      <li><a href="#">Unicorns</a></li>
      <li><a href="#">Narwhals</a></li>
      <li><a href="#">Rhinoceroses</a></li>
      <li><a href="#">Elasmotheriums</a></li>
    </ul>
  </nav>
</header>
```

![](nav-basic-html.png)

Our goal is to get each of the navigation items side-by-side in one row. To start we target their direct parent element & apply `display: flex`:

```css
nav ul {
  list-style-type: none; /* Don’t forget to remove the bullets */
  padding: 0; /* And that extra space on lists! */
  margin: 0;

  /* This is the magic, but must be put on parent elements! */
  display: flex;
}
```

![](nav-display-flex.png)

This gets us pretty close, but I would like a little spacing and distribution on the links, so we’ll add `justify-content`:

```css
nav ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: space-between;
}
```

![](nav-justify-between.png)

Although, I think that’s maybe too spaced out, so let’s get them in the centre:

```css
nav ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: center;
}
```

![](nav-justify-center.png)

With a little bit of `margin` around them everything looks great:

```css
nav li {
  margin: 0 .4em;
}
```

![](nav-justify-margins.png)

*That’s all—two (ish) lines of CSS!*

---

## Flexbox columns

We can use flexbox to get HTML elements beside each other on the same row to make grids & columns. So, let’s quickly look at how to make two pieces of content side-by-side.

We’ll start with the basic HTML setup:

```html
<section class="columns">
  <div>
    <img src="images/elasmotherium.jpg" alt="">
    <h2>Elasmotherium</h2>
    <p>An extinct genus of rhinoceros endemic to Eurasia during the Late Pliocene through the Pleistocene.</p>
    <a href="#">Read more</a>
  </div>
  <div>
    <img src="images/arsinoitherium.jpg" alt="">
    <h2>Arsinoitherium</h2>
    <p>An extinct genus of paenungulate mammals belonging to the extinct order Embrithopoda; related to elephants, sirenians, hyraxes and the extinct desmostylians</p>
    <a href="#">Read more</a>
  </div>
</section>
```

Next up we’ll target the `<section>` and turn it into a flex container.

```css
.columns {
  display: flex;
}
```

![](columns-flex.jpg)

The two `<div>` tags, because they are direct children of the `.columns` are now side-by-side flex items. But things are a little funky—nothing a little `width` won’t fix:

```css
.columns div {
  width: 50%;
}
```

![](columns-width.jpg)

That works to get the columns touching & close together, but if we want a little surrounding space we could use `padding`:

```css
.columns div {
  width: 50%;
  padding: .5em;
}
```

![](columns-padding.jpg)

### Distributing content evenly

One thing you’ll see—with your designer eye—in the layout above is that the “Read more” buttons don’t align with each other—we can overcome that with another flexbox container.

```css
.columns div {
  width: 50%;
  padding: .5em;
  display: flex;
  flex-direction: column;
}
```

This new flex container is in the `column` direction, which adjusts the location of the items vertically.

And the last little bit is to choose what element will expand to fill the space—`flex-grow` will help with that:

```css
.columns p {
  flex-grow: 1;
}
```

![](columns-flex-grow.jpg)

*Do notice how we got extra space between the `<p>` & `<h2>` tags.* That’s because margins do not collapse within a flex container—so we are seeing the margins from both the `<p>` & `<h2>` tags.

---

## Video list

- [Flexbox: introduction](https://www.youtube.com/watch?v=mQ1iWdfzvgA&index=1&list=PLWjCJDeWfDdcae7fPzpUclV89TYFOa2Vq)
- [Flexbox: wrapping rows](https://www.youtube.com/watch?v=An-FI9TKkqY&index=2&list=PLWjCJDeWfDdcae7fPzpUclV89TYFOa2Vq)
- [Flexbox: direction](https://www.youtube.com/watch?v=ff0T4kz4qDc&index=3&list=PLWjCJDeWfDdcae7fPzpUclV89TYFOa2Vq)
- [Flexbox: horizontal navigation](https://www.youtube.com/watch?v=b9siX4lCs_o&index=4&list=PLWjCJDeWfDdcae7fPzpUclV89TYFOa2Vq)
- [Flexbox: columns](https://www.youtube.com/watch?v=P2oSp_N-I7s&list=PLWjCJDeWfDdcae7fPzpUclV89TYFOa2Vq&index=5)

## Supplemental links

- [**A Complete Guide to Flexbox**](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [**Flexy Boxes**](http://the-echoplex.net/flexyboxes/)
- [**Flexbox Cheatsheet**](https://darekkay.com/dev/flexbox-cheatsheet.html)
- [Flexbox Cheatsheet](http://yoksel.github.io/flex-cheatsheet/)
- [**How Flexbox works — explained with big, colorful, animated gifs**](https://medium.freecodecamp.org/an-animated-guide-to-flexbox-d280cf6afc35)
- [**Even more about how Flexbox works — explained in big, colorful, animated gifs**](https://medium.freecodecamp.org/even-more-about-how-flexbox-works-explained-in-big-colorful-animated-gifs-a5a74812b053)
- [The Ultimate Flexbox Cheat Sheet](https://www.sketchingwithcss.com/samplechapter/cheatsheet.html)
- [Learn Flexbox for Free](https://scrimba.com/g/gflexbox)
- [Flexbox Cheatsheet](https://yoksel.github.io/flex-cheatsheet/)
- [Flexbox Cheatsheet](http://jonibologna.com/flexbox-cheatsheet/)
- [Understanding Flexbox: Everything you need to know](https://medium.freecodecamp.org/understanding-flexbox-everything-you-need-to-know-b4013d4dc9af)
- [The Ultimate Guide to Flexbox — Learning Through Examples](https://medium.freecodecamp.org/the-ultimate-guide-to-flexbox-learning-through-examples-8c90248d4676)
- [Flexbox: How Big Is That Flexible Box?](https://www.smashingmagazine.com/2018/09/flexbox-sizing-flexible-box/)
- [Flexbox use cases](https://www.smashingmagazine.com/2018/10/flexbox-use-cases/)
- [Flexbox guides on MDN](https://hacks.mozilla.org/2018/01/new-flexbox-guides-on-mdn/)
- [Laying Out A Flexible Future For Web Design With Flexbox Best Practices](https://www.smashingmagazine.com/2015/08/flexible-future-for-web-design-with-flexbox/)
- [Almost complete guide to flexbox (without flexbox)](https://kyusuf.com/post/almost-complete-guide-to-flexbox-without-flexbox)
