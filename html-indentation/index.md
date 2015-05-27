---
group: web-dev-1
playlist: PLWjCJDeWfDdey4UwR8TkNLt6VZ2hlWyo-
download: https://github.com/acgd-learn-the-web/html-indentation/archive/master.zip
github: https://github.com/acgd-learn-the-web/html-indentation-code
---

Indentation is a helpful practice when writing code—indentation is for developers, not for computers.

---

## Why indent HTML

When writing HTML it’s a really great idea to indent elements.

The indentation isn’t for the browser—browser’s don’t care. The indentation is for us to help understand our code.

Indentation is extremely helpful for a few reasons:

- Helps us understand what elements are inside other elements
- Helps us see validation errors more clearly
- Helps maintain our code because it’ll be more obvious if we haven’t look at it in a while
- Shows a sense of craftsmanship and care

---

## Indent child elements

Whenever an element is unique and inside another element it should be indented:

```html
<body>
  <header>
    <h1>All About Apatosaurus</h1>
  </header>
</body>
```

- Because the `<h1>` is inside the `<header>` it gets indented.
- Because the `<header>` is inside the `<body>` it gets indented, as well as all the elements inside it.

### Not all children must be indented

We don’t always have to indent child elements if the line is understandable.

```html
<nav>
  <ul>
    <!-- The <a> tag isn't indented because it's the only tag -->
    <li><a href="#">Herbivorous dinosaurs</a></li>
    <li><a href="#">Omnivorous dinosaurs</a></li>
    <li><a href="#">Carnivorous dinosaurs</a></li>
  </ul>
</ul>
```

But, you could write this another way, if it makes more sense for you:

```html
<nav>
  <ul>
    <li>
      <!-- The <a> tag is now indented and on its own line for clarity -->
      <a href="#">Herbivorous dinosaurs</a>
    </li>
    <li>
      <a href="#">Omnivorous dinosaurs</a>
    </li>
    <li>
      <a href="#">Carnivorous dinosaurs</a>
    </li>
  </ul>
</nav>
```

Another case where children shouldn’t be indented is in when the element is a text-level element:

```html
<p>The <b>Iguanodon</b> is a large bipedal dinosaur.</p>
```

The `<b>` tag shouldn’t be indented because it’s wrapped around text that’s embedded in another element.

### Don’t over indent

Be careful with indentation, only indent when an element is **inside** another element.

The below example is wrong:

```html
<article>
  <h2>Stegosaurus</h2>
    <img src="stego.jpg" alt="">
      <p>The Stegosaurus has huge plates and a spiky tail.</p>
</article>
```

The `<img>` and `<p>` tags shouldn’t be indented because they aren’t inside other elements.

The above sample should be written like this:

```html
<article>
  <h2>Stegosaurus</h2>
  <img src="stego.jpg" alt="">
  <p>The Stegosaurus has huge plates and a spiky tail.</p>
</article>
```

The `<h2>`, `<img>` and `<p>` all align because they are all directly inside the `<article>`.

*If you code editor has “Indent guides”, turn them on. They create nice vertical lines that help you see the alignment of long pieces of code.*

---

## Further organization

There’s a few other ways we can increase the maintainability and clarity of our HTML.

### Vertical spacing

Consider adding blank lines in the HTML to create separations between sections.

```html
<article>

  <h1>Pteranodon</h1>

  <ul>
    <li>Flys</li>
    <li>Has a long beak</li>
  </ul>

</article>
```

Notice the blank lines after `<article>` and before and after the `<ul>`. They create some whitespace to help our eyes focus. As designers, we know how important whitespace is.

### Comments

Commenting sections of HTML is also very helpful in seeing the groups.

```html
<div class="banner-group">

  <div class="banner">…</div>

  <div class="intro">
    <p>Intro</p>

    <div class="sub-intro">
      Sub intro
    </div> <!-- End .sub-intro -->
  </div> <!-- End .intro -->

</div> <!-- End .banner-group -->
```

The above example uses whitespace and comments to add clarity. Notice I’ve comment the three closing `</div>` tags—without the comments it’s just three tags in a row without much understanding of their purpose.

### Attribute ordering

Many developers find that ordering the attributes within an element helps them find the information they want.

As an example, with and `<img>` tag we could put the attributes in this order:

```html
<img class="…" id="…" href="…" alt="…">
```

The attributes are ordered so that the most referenced, therefore most important, attributes are closer to the front of the tag. If the important attributes were further to the right there’s a higher change they’d be difficult to find or hidden off the side of the screen.

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

```html
<body>
··<header> <!-- Space indentation may look like this -->
····<h1>All About Apatosaurus</h1>
» </header> <!-- Tab indentation may look like this -->
</body>¬ <!-- Lots of editors even show where return was pressed -->
```

---

## Video list

1. [HTML indentation: how to indent](https://www.youtube.com/watch?v=FV2td6KJNVA&index=1&list=PLWjCJDeWfDdey4UwR8TkNLt6VZ2hlWyo-)
2. [HTML indentation: spacing & comments](https://www.youtube.com/watch?v=9cCKhhmUppo&index=2&list=PLWjCJDeWfDdey4UwR8TkNLt6VZ2hlWyo-)
3. [HTML indentation: attribute ordering](https://www.youtube.com/watch?v=CisOD-PXTKU&index=3&list=PLWjCJDeWfDdey4UwR8TkNLt6VZ2hlWyo-)
4. [HTML indentation: tabs vs. spaces](https://www.youtube.com/watch?v=ee1Ox3zbKZs&list=PLWjCJDeWfDdey4UwR8TkNLt6VZ2hlWyo-&index=4)
