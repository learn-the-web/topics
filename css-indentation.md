---
title: "CSS indentation"
tags: "css indentation tabs spaces hierarchy vertical alignment monospace fonts"
desc: "The proper method for indenting CSS to make it understandable by you and your team."
playlist: PLWjCJDeWfDdcYd1EDEy4HPi7Mjiv8Tmyr
download: https://github.com/acgd-learn-the-web/css-indentation-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/css-indentation-code
extra_practice:
  exercises:
    - title: "CSS validation fixes"
      url: "/courses/web-dev-1/week-05/#css-validation-fixes"
---

Indentation is a helpful practice when writing code—indentation is for developers, not for computers.

---

## Why indent CSS

When writing CSS it’s a really great idea to indent properties within a rule set.

The indentation isn’t for the browser—browser’s don’t care. The indentation is for us to help understand our code.

Indentation is extremely helpful for a few reasons:

- Helps us understand what selector properties are associated with
- Helps us see validation errors more clearly, especially missing closing curly braces
- Helps maintain our code because it’ll be more obvious if we haven’t look at it in a while
- Shows a sense of craftsmanship and care

---

## Indent properties

Whenever you write a property to adjust something in your design, indent the property inside the rule set.

```css
h1 {
  font-size: 2rem;
  font-weight: bold;
}
```

Because the `font-size` and `font-weight` affect the `<h1>` they’re indented.

---

## Put selectors on unique lines

Another way to organize CSS is to put each selector on its own line so it’s more obvious there’s many selectors.

```css
h1,
h2,
h3 {
  color: orange;
}
```

Notice how each different different selector (`h1`, `h2`, `h3`) are on their own line. This aids understanding because if they were on the same line we may, with a quick glance, confuse them for a single selector.

---

## Further organization

There’s a few other ways we can increase the maintainability and clarity of our CSS.

### Indent selectors of child elements

When a selector in CSS represents an element in HTML that’s a child element of another selector, indent it.

Here’s some example HTML:

```html
<div class="banner">
  <img class="banner-img" src="…" alt="">
  <div class="banner-content">
    <h2>…</h2>
    <p>…</p>
  </div>
</div>
```

Looking at the structure of that HTML, we can see that the `.banner-content` is inside of `.banner`.

To help us understand our HTML more clearly from inside our CSS, we can use indentation, like this:

```css
.banner {
  ⋮
}

  .banner-img {
    ⋮
  }

  .banner-content {
    ⋮
  }
```

Looking at this CSS, it’s more obvious for us that `.banner-img` is a child element of `.banner`.

#### Indent media queries

This indentation also makes sense for CSS inside media queries, to make it obvious that the CSS is inside.

```css
.banner {
  ⋮
}

@media print {

  .banner {
    ⋮
  }

}
```

### Comments

Commenting sections of CSS is also very helpful in seeing the groups.

```css
/* ------------- =General -------------- */

html { … }
body { … }

/* ------------- =Masthead -------------- */

.masthead { … }
.nav { … }
  .nav a { … }

/* ------------- =Typography -------------- */

h1 { … }
p { … }
ul { … }

```

We can use CSS comments (with fake lines) to create separation in our CSS.

Lots of people like to put an `=` in front of the title to make searching with their code editor easier.

### Property ordering

Many developers also like to order the properties within the rule set. There are different ways to do it: alphabetical, logical grouping, etc.

The system I follow is both grouping by purpose and alphabetical—because I’m super obsessive.

```css
header {
  /* Box model */
  margin: 0 0 1rem;
  padding: 0.5em;

  /* Visual decorations */
  background-color: darkgreen;
  border: 1px solid green;

  /* Typography */
  color: red;
  font-family: sans-serif;
}
```

I have three different sections in the rule set:

1. *box model* — `margin`, `padding`, `position`, `width`, etc.
2. *visual decorations* — `background`, `border`, `transform`, `outline`, etc.
3. *typography* — `color`, `font`, `text-decoration`, etc.

*You’ll also notice that each grouping is also alphabetized.*

If is difficult at first to get into the habit of organizing your code this way, but eventually it becomes second nature and you do it without thinking. *In fact, in the videos, if I don’t write my code this way it’s because I’m making a concerted effort not to.*

**Links**

- [**CSS-Tricks: Breaking Up Large Files Into Sections**](https://css-tricks.com/breaking-up-large-files-into-sections/)

---

## Tabs vs. spaces

When indenting your code it’s a good idea to choose to either indent with the tab character or with a space.

Most code editors will seamlessly convert between the two. And most editors will even insert spaces instead of tab characters using the tab key if set up to do so—called “Soft tabs”.

### Tab specifics

- Adjustable width spacing, each team member can have different thicknesses of indentation
- Some markup and programming languages don’t work well with tab indentation

### Space specifics

- Consistency across platforms, editors, and applications
- Can’t adjust the indentation width very easily

### Be consistent

*Choose what’s best for you and for your team and be consistent.*

- Don’t mix tabs and spaces in the same file.
- Don’t mix tabs and spaces in the same project.

### Invisible characters

Turning on the invisible characters in your code editor is extremely helpful in seeing what characters you’ve typed into the file.

Very often a space will be shown as a tiny dot & tabs will be shown and little arrows or lines. With these indicators it’s very obvious what you’ve typed.

```css
html {
··font-size: 100%; /* Space indentation may look like this */
» background-color: #e2e2e2; /* Tab indentation may look like this */
}¬ /* Lots of editors even show where return was pressed */
```
---

## Video list

1. [CSS indentation: how to indent](https://www.youtube.com/watch?v=mpaJ_bA6Wrg&index=1&list=PLWjCJDeWfDdcYd1EDEy4HPi7Mjiv8Tmyr)
2. [CSS indentation: spacing & comments](https://www.youtube.com/watch?v=2v6KJhJ0_fQ&index=2&list=PLWjCJDeWfDdcYd1EDEy4HPi7Mjiv8Tmyr)
3. [CSS indentation: ordering properties](https://www.youtube.com/watch?v=4fCfvrYg_SM&index=3&list=PLWjCJDeWfDdcYd1EDEy4HPi7Mjiv8Tmyr)
4. [CSS indentation: tabs vs. spaces](https://www.youtube.com/watch?v=Pa_A0PQQBdE&index=4&list=PLWjCJDeWfDdcYd1EDEy4HPi7Mjiv8Tmyr)

## Supplemental links

- [CSS Guidelines](http://cssguidelin.es/)
- [Code Guide](http://codeguide.co/)
- [Trello CSS Guide](https://gist.github.com/bobbygrace/9e961e8982f42eb91b80)
- [Idiomatic CSS](https://github.com/necolas/idiomatic-css)
- [Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.html)
