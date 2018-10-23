---
title: "Flexbox"
tags: "css advanced layout flexbox align content justify vertical"
desc: "Learn how to use the flexbox layout system to create more advanced layouts with columns and alignments."
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

### Targets the direct children

### Boxes: block & inline

### Say goodbye to margin collapse

---

## Justification & alignment

### Justifying content

### Aligning content

### Ordering content

---

## Vertically flexible & wrapping

### Opposite flex direction

### Wrapping flex items

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

![](basic-html.png)

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

![](display-flex.png)

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

![](justify-between.png)

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

![](justify-center.png)

With a little bit of `margin` around them everything looks great:

```css
nav li {
  margin: 0 .4em;
}
```

![](justify-margins.png)

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
  justify-content: stretch;
}
```

This new flex container is in the `column` direction, which adjusts the location of the items vertically. We then used `justify-content: stretch` to make sure both of the `<div>` tags are the same height.

And the last little bit is to choose what element will expand to fill the space—`flex-grow` will help with that:

```css
.columns p {
  flex-grow: 1;
}
```

![](columns-flex-grow.jpg)

*Do notice how we got extra space between the `<p>` & `<h2>` tags.* That’s because margins do not collapse within a flex container—so we are seeing the margins from both the `<p>` & `<h2>` tags.

---

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
- [What Happens When You Create A Flexbox Flex Container?](https://www.smashingmagazine.com/2018/08/flexbox-display-flex-container/)
- [Flexbox: How Big Is That Flexible Box?](https://www.smashingmagazine.com/2018/09/flexbox-sizing-flexible-box/)
- [Flexbox guides on MDN](https://hacks.mozilla.org/2018/01/new-flexbox-guides-on-mdn/)
- [Laying Out A Flexible Future For Web Design With Flexbox Best Practices](https://www.smashingmagazine.com/2015/08/flexible-future-for-web-design-with-flexbox/)
- [Almost complete guide to flexbox (without flexbox)](https://kyusuf.com/post/almost-complete-guide-to-flexbox-without-flexbox)
