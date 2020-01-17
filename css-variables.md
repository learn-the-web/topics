---
title: "CSS variables"
tags: "css variables custom properties maintenance reusuability root var colours fonts"
desc: "Using CSS variables & custom properties to generate more maintainable colour and font systems."
playlist: PLWjCJDeWfDdcFjcJzZ8jEkIcQdzpV6AbJ
download: https://github.com/acgd-learn-the-web/css-variables-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/css-variables-code
---

CSS variables give us lots of flexibility within our code, allow us to reduce duplication and enforce standards while still sitting within CSS’s cascade.

---

## What & why of variables

Often we have information in our CSS that we want to reuse, like colours & sizes. From a programming perspective we don’t want to repeat that information every time we need to use it.

```css
h2 {
  color: olivegreen;
}

.highlight {
  color: olivegreen;
}
```

In the above example of code, if we wanted to change that colour or use it in another place we’d have to use search & replace or dig through you CSS to find the correct colour.

Imagine we could write and document that colour in one place in our code & then refer to it whenever we want to use it.

## Creating variables

CSS variables—actually CSS custom properties—can be defined just about anywhere in your CSS. Inside any block.

CSS variables always begin with two dashes—then you make up the rest.

```css
.dino {
  --head-color: green;
  --plate-color: brown;
}
```

One common place to define custom properties is at the top of the CSS file in a special block called `:root`

```css
:root {
  --base-font-size: 110%;
  --font-primary: Georgia, serif;
}
```

*The `:root` declaration is accessible to all of your CSS—it’s making the variables global.*

### Using variables

After we’ve defined our CSS variables we can use them in our CSS code with the `var()` function. The `var()` function grabs the information stored in the variable and puts it in the same place—think of it like a placeholder for the actual information stored in the variable.

```css
h1 {
  font-family: var(--font-primary);
}

.caption {
  font-family: var(--font-primary):
}
```

Both of those elements will now inherit the value of our `--font-primary` variable and use it. If we want to change the primary font we only need to change it inside the `:root` selector and **all** instances will immediately change.

### Any value you want

You can use variables for just about any value you’d like. Here are some quick examples.

```css
:root {
  --base-font-size: 100%;
  --base-line-height: 1.5em;
  --color-primary: #f33;
}

html {
  font-size: var(--base-font-size);
  line-height: var(--base-line-height);
}

h1 {
  color: var(--color-primary);
  margin: 0 0 var(--base-line-height);
}
```

*As long as the type of information store in the variable matches the expected information where it’s being used—you can do it!*

#### Numerical variables with calc()

You can even use those variables to create new variables:

```css
.card {
  padding: calc(var(--base-line-height) / 2);
}
```

Above we made padding on our card equal to half the size of our base line height!

---

## Variables & the cascade

One amazing thing about CSS variables is they can be adjusted by the cascade. Here’s an example using some buttons.

Let’s first make our default button using some variables.

```css
:root {
  --color-primary: black;
  --color-primary-opposite: white;
}

.btn {
  border: 4px solid var(--color-primary);
}
```

This creates a button with a black border around it. Maybe we have a banner, where the background colour of the banner is black—the button’s border would no longer be visible.

```html
<div class="banner">
  <h1>Quetzalcoatlus</h1>
  <a class="btn">See more</a>
</div>
```

```css
.banner {
  background-color: black;
}
```

So now we have to change the button’s border colour. We could do that by rewriting the `border` itself or be redefining the variable.

Change what the `--color-primary` variable means within the `.banner`:

```css
.banner {
  background-color: black;
  --color-primary: var(--color-primary-opposite);
}
```

*We are redefining what `--color-primary` means to all the children elements of `.banner`—the variable is inherited through the CSS cascade.*

### Variables & media queries

The same technique can be applied with media queries. Let’s make a very simple type system.

```css
:root {
  --font-size-primary: 100%;
  --font-line-height-primary: 1.3;
}

html {
  font-size: var(--font-size-primary);
  line-height: var(--font-line-height-primary);
}

h1 {
  font-size: calc(var(--font-size-primary) * 2);
  margin: 0 0 var(--font-line-height-primary);
}

p {
  margin: 0 0 var(--font-line-height-primary);
}
```

In our simple type system we’re setting matching font sizes and line heights.

When we get to larger screen sizes maybe we want to make those slightly larger. It’s simple with media queries: we just redefine the variables.

```css
@media only screen and (min-width: 38em) {

  :root {
    --font-size-primary: 110%;
    --font-line-height-primary: 1.4;
  }

}
```

All of the elements that use those variables will automatically grow & change without writing any more CSS.

---

## Variables inside SVG spritesheets

We can even use CSS variables with SVG spritesheets (and embeded SVGs)! A common reason to do this is for changing the colours of the SVG fills when hovered. Let’s look at a super simplified example.

```svg
<svg>
  <symbol id="icon" viewBox="0 0 256 256">
    <circle fill="var(--color-icon)" cx="128" cy="128" r="128"/>
  </symbol>
</svg>
```

Notice how we’ve defined the colour of the SVG’s circle with a CSS variable.

Let’s insert it into our HTML:

```html
<a class="btn" href="#">
  <svg><use xlink:href="#icon"></use></svg>
  <span>It’s a planet</span>
</a>
```

With a little bit of CSS & CSS custom properties we can make that colour change on hover.

```css
.btn {
  --color-icon: orange;
}

.btn:hover {
  --color-icon: limegreen;
}
```

But that’s just a quick example, you could use it for animations, transitions, locations, anything!

---

## Video list

- [CSS variables: making variables](https://www.youtube.com/watch?v=ylq9BR0lK70&list=PLWjCJDeWfDdcFjcJzZ8jEkIcQdzpV6AbJ&t=0s&index=2)
- [CSS variables: using the cascade](https://www.youtube.com/watch?v=vIitq8IJbHY&list=PLWjCJDeWfDdcFjcJzZ8jEkIcQdzpV6AbJ&t=0s&index=3)
- [CSS variables: inside media queries](https://www.youtube.com/watch?v=tDT7BGyPU2I&list=PLWjCJDeWfDdcFjcJzZ8jEkIcQdzpV6AbJ&t=0s&index=4)
- [CSS variables: inside SVG spritesheets](https://www.youtube.com/watch?v=HmqCCHxVJyA&list=PLWjCJDeWfDdcFjcJzZ8jEkIcQdzpV6AbJ&t=0s&index=5)

## Supplemental links

- [Learn CSS Variables](https://scrimba.com/g/gcssvariables)
- [How to make responsiveness super simple with CSS Variables](https://medium.freecodecamp.org/how-to-make-responsiveness-super-simple-with-css-variables…)
- [Everything you need to know about CSS Variables](https://medium.freecodecamp.org/everything-you-need-to-know-about-css-variables-c74d922ea8…)
- [Multi-Colored SVG Symbol Icons with CSS Variables](https://frontstuff.io/multi-colored-svg-symbol-icons-with-css-variables)
- [Animating with CSS Variables](http://valhead.com/2017/07/21/animating-with-css-variables/)
- [A Practical Guide to CSS Variables (Custom Properties)](https://www.sitepoint.com/practical-guide-css-variables-custom-properties/)
