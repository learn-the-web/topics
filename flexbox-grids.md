---
title: "Flexbox grids"
tags: "grids flexbox modular columns rows units responsive web design screens adjustments"
desc: "Creating and using a modular, responsive grid system on a website to simplify layout."
playlist: PLWjCJDeWfDdeUChfM6TV2U7jzQVRjsu60
download: https://github.com/learn-the-web/flexbox-grids-code/archive/master.zip
github: https://github.com/learn-the-web/flexbox-grids-code
cheatsheet: gridifier-cheat-sheet
tool:
  name: Gridifier
  url: "https://gridifier.web-dev.tools"
extra_practice:
  week:
    title: "Web Dev 2, Week 02"
    url: "/courses/web-dev-2/week-02/"
  slides:
    - title: "Grid systems"
      url: "/courses/web-dev-2/grid-systems/"
  lessons:
    - title: "Using Gridifier"
      url: "/courses/web-dev-2/using-gridifier/"
  activities:
    - title: "Grid Genius"
      url: "grid-genius"
  exercises:
    - title: "Grid layout"
      url: "/courses/web-dev-2/week-02/#grid-layout"
    - title: "Hot grid-dle"
      url: "/courses/web-dev-2/week-03/#hot-grid-dle"
    - title: "Grid-ception"
      url: "/courses/web-dev-2/week-03/#grid-ception"
---

Making flexible and responsive grids using HTML & CSS to simplify & systemize the creation of responsive websites.

---

## Flexible grids

Flexible grids in CSS are composed of nested `<div>` elements within a row. (Well you could use any element really.)

We have one element, the “row”, that surrounds a bunch of other elements, the “columns”. Each of the columns are then positioned in CSS to be beside each other.

```html
<div class="grid">
  <div class="unit">Grid Unit 1</div>
  <div class="unit">Grid Unit 2</div>
  <div class="unit">Grid Unit 3</div>
</div>
```

Within CSS, we can then use flexbox to arrange the units to fit beside each other. We probably want to include `flex-wrap` to allow for more responsive grids.

```css
.grid {
  display: flex;
  flex-wrap: wrap;
}

.unit {
  /* The width is set to 33% because we want to fit three columns in our row. */
  width: 33.3333%;
}
```

This will create a grid row with three columns inside that flex with the width of the browser because they are sized using percentages.

The major problem is that there is no space, or gutter, between each column.

To solve the problem in the most flexible manner, we can put another class on the unit to add the gutter’s padding.

```html
⋮
<div class="unit gutter">
  Grid 1
</div>
⋮
```

```css
.gutter {
  padding-left: 1em;
  padding-right: 1em;
}
```

Using a `.gutter` gives us the flexibility to choose whether we want padding or not.

So we could create grid units with full bleed images.

```html
⋮
<div class="unit">
  <img src="https://placehold.it/500x500" alt="">
</div>
⋮
```

*If you combine the grid system with the modular typography system you’ll see that the type system comes with a series of gutter classes relative to your type size.*

We can also create a column in our grid that takes up ⅔ of the available space—a column that is double width.

```html
⋮
<div class="unit unit-2-3">
  Double Width 1
</div>
⋮
```

```css
.unit-2-3 {
  width: 66.6667%;
}
```

Setting our grid systems in percentages give them flexibility because we can never guarantee what size a browser window is going to be.

---

## Responsive grids

We can extend our flexible grids to be responsive using a technique with multiple classes on our `<div>` elements.

```html
<div class="grid">
  <div class="unit unit-s-1 unit-m-1 unit-l-1-3">Grid Unit 1</div>
  <div class="unit unit-s-1 unit-m-1-2 unit-l-1-3">Grid Unit 2</div>
  <div class="unit unit-s-1 unit-m-1-2 unit-l-1-3">Grid Unit 3</div>
</div>
```

You’ll notice multiple classes on each of the `.unit` `<div>` elements.

Each class represents the width the `<div>` will be in at each different screen size.

- `unit-s-1`—means the unit takes up 100% of the space on small screens
- `unit-m-1-2`—means the unit takes up ½ the available space on medium screens
- `unit-l-1-3`—means the unit takes up ⅓ the available space on large screens

In our CSS we would then create these classes and style them within different media queries.

```css
.unit-s-1 {
  width: 100%;
}

@media only screen and (min-width: 38em) {

  .unit-m-1 {
    width: 100%;
  }

  .unit-m-1-2 {
    width: 50%;
  }

}

@media only screen and (min-width: 60em) {

  .unit-l-1-3 {
    width: 33.3333%;
  }

}
```

Following the mobile-first approach we set the small sized units outside media queries and then add media queries for the larger screen sizes.

As the screen changes size the units will fall into place beside each other or stack depending on the available screen space.

I like to work in fractions for my grid sizes because, to me, it makes the most sense online. Lots of other designers like to use a set number of columns, like 12. But to me, I would never need 12 columns on a mobile screen so it doesn’t make sense.

---

## Complete grid system

A complete grid system would be composed of rows that can have thirds, quarters, fifths, etc. As many columns as you’d like.

Grid systems also have a series of other capabilities:

1. `hidden` classes provide the ability to hide & show units in specific screen sizes.
2. `offset` classes provide the ability to push units way from the edge of the screen and other units.
3. `push` & `pull` classes allow you to move units around, reordering them.
4. `top`, `bottom` & `middle` alignment classes for moving the units vertically.

**[Check out Gridifier](https://gridifier.web-dev.tools)**, a tool I created for myself to generate the code for a responsive grid system.

### Pre-built grid frameworks

There’s lots of prototyping frameworks online that come setup with a themes, grids, type systems, and components to help you create a quick website.

A few of the most common ones are:

- [Bootstrap](http://getbootstrap.com/)
- [Foundation by Zurb](http://foundation.zurb.com/)
- [Pure by Yahoo](http://purecss.io/)
- [Gridset](https://gridsetapp.com/)

**Links**

- [Net.Tuts+: Mobile First with Bootstrap 3](http://net.tutsplus.com/tutorials/html-css-techniques/mobile-first-with-bootstrap-3/)
- [SitePoint: Understanding Twitter Bootstrap 3](http://www.sitepoint.com/understanding-twitter-bootstrap-3/)

---

## Video list

1. [Flexbox grids: flexible grids](https://www.youtube.com/watch?v=sYASH-3iGNQ&t=0s&list=PLWjCJDeWfDdeUChfM6TV2U7jzQVRjsu60&index=1)
2. [Flexbox grids: responsive grids](https://www.youtube.com/watch?v=FOLRicY70lE&list=PLWjCJDeWfDdeUChfM6TV2U7jzQVRjsu60&t=0s&index=2)
3. [Flexbox grids: hiding units on different screen sizes](https://www.youtube.com/watch?v=9Y8IyXFqbNU&list=PLWjCJDeWfDdeUChfM6TV2U7jzQVRjsu60&index=3)
4. [Flexbox grids: simplifying fractions for unit sizes](https://www.youtube.com/watch?v=BNFKLqYl8rU&list=PLWjCJDeWfDdeUChfM6TV2U7jzQVRjsu60&index=4)
5. [Flexbox grids: pushing units aside using offsets](https://www.youtube.com/watch?v=kVMdNbrHgbQ&list=PLWjCJDeWfDdeUChfM6TV2U7jzQVRjsu60&index=5)
6. [Flexbox grids: grids inside grids](https://www.youtube.com/watch?v=hpwjNC4Eo-U&list=PLWjCJDeWfDdeUChfM6TV2U7jzQVRjsu60&index=6)

## Supplemental links

1. [A List Apart: Content-out Layout](http://alistapart.com/article/content-out-layout)
