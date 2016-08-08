---
playlist: PLWjCJDeWfDdeinzeLY9NvJxOaCR_inrTI
download: https://github.com/acgd-learn-the-web/media-queries-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/media-queries-code
cheatsheet: screen-sizes-cheat-sheet
---

Media queries are the backbone of responsive web design, allowing us to change our layouts and designs based on the browser.

---

## What are media queries?

Media queries are CSS declarations that allow us to detect certain features of our browser then write different CSS to for that purpose.

We can detect the width & height of the screen; the screen density; the orientation; and many newer features.

By far, width is the most common media query variable, used so we can change the layout of our website for different screen sizes.

### Media query syntax

Media query syntax is just one new line of CSS that wraps around other CSS. All the CSS rule sets inside the media query are only applied if the condition of the media query is met.

```css
h1 {
  color: red;
}

@media only screen and (min-width: 650px) {

  h1 {
    color: green;
  }

}
```

In the above code example, the `<h1>` will be green if the screen’s width is at least 650 pixels wide.

We could even add another media query afterwards, changing the colour again.

```css
@media only screen and (min-width: 980px) {

  h1 {
    color: blue;
  }

}
```

Now when the screen has a width of at least 980 pixels the `<h1>` will be blue.

#### Understanding min-width & the cascade

The `min-width` measurement is the most common, though there is also `max-width`. Since we are making our websites mobile first, that means that all the CSS that targets small screens should be at the top of our website, outside media queries.

Then we put our media queries after the small screen CSS to make minor adjustments to our layout.

*When using `min-width` we have to remember that the sizes cascade—each min-width media query adding onto the one above.*

```css
h1 {
  color: red;
}

@media only screen and (min-width: 650px) {

  h1 {
    color: green;
    text-decoration: underline;
  }

}

@media only screen and (min-width: 980px) {

  h1 {
    color: blue;
  }

}
```

In the above code, we add `text-decoration` to our `<h1>` at 650 pixels. At 980 pixels you can see the `text-decoration` is not declared again, but it would still be visible because a screen that’s at least 980px wide is still at least 650px wide. *The properties cascade and inherit to larger media queries.*

If in the 980px media query we no longer wanted the `text-decoration` we’d have to explicitly remove it:

```css
@media only screen and (min-width: 980px) {

  h1 {
    color: blue;
    text-decoration: none;
  }

}
```

**It’s extremely important that you style the small screen first, then add media queries afterwards to adjust the layout for bigger screens.**

**Start with the smallest min-width media query, then the next size, and continue upwards. If the min-width sizes get out of order the layout will not do what you want.**

If you start designing on big screens it’s extremely difficult to work backwards. *So: mobile-first.*

### When to add a media query

The best point to add a media query is by looking at your layout and watching for awkward content points.

- Does the line length get too long?
- Could the navigation fit all on one line?
- Is the image too small? Or too big?
- Is there a lot of wasted space?
- Is the text too tight?

Our primary concern with media queries is content awkwardness. If it looks weird or could be better, add a media query. But remember to always style the small screen first.

### Where to put your media queries

I like to group my media queries immediately with the content they affect. So if ̛I’m styling my navigation, the media query goes immediately after the small screen navigation styles.

```css
/* More CSS above here */

.nav {
  margin: 0;
}

@media only screen and (min-width: 650px) {

  .nav {
    text-align: center;
  }

  .nav li {
    display: inline-block;
  }

}

@media only screen and (min-width: 980px) {

  ⋮

}

/* More CSS below here */
```

Other people like to put all their media queries at the bottom of the CSS. Doing this way is good if you only have one CSS file, but if you get into more complex websites with multiple CSS files it starts to make less sense.

### Other query variables

We’ve concentrated mostly on `min-width` but there’s lots of other variables to detect:

```css
@media only screen and (min-height: 480px) { … }

/* Be really careful with max-width, only use them as a last resort */
@media only screen and (max-width: 650px) { … }
@media only screen and (max-height: 480px) { … }

/* For print styles: discussed below */
@media print { … }

/* Screen orientation */
@media only screen and (orientation: landscape) { … }
@media only screen and (orientation: portrait) { … }

/* Screen pixel density */
@media only screen and (min-resolution: 1.5ddpx) { … }

/* Detecting monochrome screens like Kindle */
@media screen and monochrome { … }

/* Interaction types, still experimental */
@media (pointer: fine) { … } /* Has a mouse */
@media (pointer: course) { … } /* Touch with thick thumbs */
@media (hover: hover) { … } /* Can hover with a mouse */
@media (scripting: enabled) { … } /* Whether Javascript is available or not */
```

**Links**

- [Interaction Media Features and their potential (for incorrect assumptions)](http://dev.opera.com/articles/media-features/)

---

## Em-based media queries

When creating our media queries for layout it’s always best to use em-based media queries. *It helps us to not think in device specific widths and concentrate more on our content.*

### Calculating em-based media queries

1. Using the developer tools, get the width of the screen in pixels where the content is awkward
2. Get your default font-size, set on your HTML element; it should be 16px
3. Divide them: 500px screen width ÷ 16 = 31.25
4. I usually round that number to something nice like 30em

### Using em-based media queries

After we’ve got our em width we just use media queries like normal:

```css
@media only screen and (min-width: 38em) { … }
@media only screen and (min-width: 60em) { … }
```

One great accessibility benefit of em-based media queries is that if our user has increased the font-size in their browser, the layout will adjust to present the text in a design that’s most appropriate for the content and the current font-size.

### Common em sizes

I’ve found a few media query em sizes have popped up over and over again when designing websites.

- `25em` — small screens, about 400px
- `38em` — medium screens, about 650px
- `60em` — large screens, about 980px
- `90em` — extra large screens, about 1500px

*That doesn’t mean these are the only sizes I use, but these are often what I’d call the “major” breakpoints.*

**[☛ Check out the screen sizes cheat sheet](/topics/screen-sizes-cheat-sheet/)**

**Links**

- [The Ems Have It: Proportional Media Queries](http://blog.cloudfour.com/the-ems-have-it-proportional-media-queries-ftw/)

---

## Creating a responsive navigation

Lets start with a basic, stacked navigation:

```html
<nav>
  <ul class="nav">
    <li><a href="#">Terrestrial planets</a></li>
    <li><a href="#">Gas giants</a></li>
    <li><a href="#">Dwarf planets</a></li>
    <li><a href="#">Asteroids</a></li>
  </ul>
</nav>
```

The CSS for our basic navigation might look something like this:

```css
.nav {
  margin: 0;
  padding: 0;
  background-color: #000;
  list-style-type: none;
}

.nav a {
  display: block;
  padding: 1em;
  color: #e2e2e2;
}

.nav a:hover {
  background-color: #444;
  color: #fff;
}
```

The above navigation works well for small screens, but on medium screens it gets a little wonky: too much horizontal space is wasted. So let’s add a media query.

```css
@media only screen and (min-width: 38em) {

  .nav {
    text-align: center;
  }

  .nav li {
    display: inline-block;
  }

}
```

So now, on our medium screen, the navigation is horizontal, all on one line.

Then, maybe on large screens we decide it should be in its own column, off to the left, so we can adjust it again with another media query.

```css
@media only screen and (min-width: 60em) {

  .nav {
    float: left;
    width: 20%;
  }

  .nav li {
    /* Re-set the display setting to overwrite the 38em MQ */
    display: block;
  }

}
```

*It’s important to notice that the media queries don’t repeat everything from the small screen styles, they only change the bits that are different.*

---

## Print styles

If your website is text heavy and is a piece of content that people may want to print out like an article, tutorial, recipe, book, etc. then spend a few minutes styling the printable version of your website.

Using media queries we can change our website when the user prints it out:

```css
@media print {
  /* Whatever CSS changes you want in here */
}
```

For many websites there’s stuff on the screen that doesn’t need to be printed our, like navigation, footers, etc. Use the print media query to hide those items.

```css
.masthead { … }
.footer { … }

@media print {

  .masthead,
  .footer {
    display: none;
  }

}
```

Some things to consider:

- Remove headers & footers
- Remove sidebars and extraneous content
- Remove background colours
- Look at what your site will look like in black & white
- Simplify the layout into one column

### Print-specific CSS properties

There’s a bunch of CSS properties that only work when a website is printed:

- `page-break-inside` — whether or not to put a page break inside something; `auto`, `avoid`.
- `page-break-before` — whether a page break should exist before something; `always`, `avoid`.
- `page-break-after` — whether a page break should exist after something; `always`, `avoid`.

### Showing hyperlink URLs

When printing a website out the hyperlinks may still be styled but our user will no long know where they point to. So in our print styles it’s a good idea to make the URL visible:

```css
@media print {

  a::after {
    content: " <" attr(href) ">";
    color: #666;
  }

}
```

The above `content` line will pull the `href` attribute from the `<a>` tags on the website and display it on the page immediately after the link.

### Styling the page

When creating print styles we can style the page, changing it’s orientation, or alignment based on left or right side pages.

The `@page` declaration allows us to target different aspects of the page.

```css
@page {
  size: landscape; /* Encourage the browser to switch to landscape paper */
}

/* Style the first-page */
@page :first {
  padding-top: 20em;
}

/* Style the left side page */
@page :left {
  margin: 25mm 50mm 25mm;
}

/* Style the right side page */
@page :right {
  margin: 25mm 25mm 25mm 50mm;
}
```

---

## Video list

1. [Media queries: introduction](https://www.youtube.com/watch?v=X8sUiRemgqU&index=1&list=PLWjCJDeWfDdeinzeLY9NvJxOaCR_inrTI)
2. [Media queries: columns](https://www.youtube.com/watch?v=pSbNxyHeioA&index=2&list=PLWjCJDeWfDdeinzeLY9NvJxOaCR_inrTI)
3. [Media queries: banner](https://www.youtube.com/watch?v=n2LxnjT68gc&index=3&list=PLWjCJDeWfDdeinzeLY9NvJxOaCR_inrTI)
4. [Media queries: toggle navigation](https://www.youtube.com/watch?v=ifhppwLzXwI&list=PLWjCJDeWfDdeinzeLY9NvJxOaCR_inrTI&index=4)
5. [Media queries: no media queries](https://www.youtube.com/watch?v=ig9pueXrl3o&list=PLWjCJDeWfDdeinzeLY9NvJxOaCR_inrTI&index=5)
6. [Media queries: print styles](https://www.youtube.com/watch?v=krZXeORLXtM&list=PLWjCJDeWfDdeinzeLY9NvJxOaCR_inrTI&index=6)

## Supplemental links

- [A List Apart: Responsive Web Design](http://www.alistapart.com/articles/responsive-web-design/)
- [Brad Frost: This is Responsive](http://bradfrost.github.com/this-is-responsive/)
- [Luke W: Multi-Device Layout Patterns](http://www.lukew.com/ff/entry.asp?1514)
- [Luke W: Off Canvas Multi-Device Layouts](http://www.lukew.com/ff/entry.asp?1569)
- [Webdesign.Tuts+: Life Beyond 960px: Designing for Large Screens](http://webdesign.tutsplus.com/articles/general/life-beyond-960px-designing-for-large-screens/)
- [Smart Phone vs. TV Size Comparison](http://www.flickr.com/photos/bruce-lawson/6714342003/)
- [Opera Dev: Creating Web Content for TV](http://dev.opera.com/articles/view/creating-web-content-for-tv/)
- [Google: Design for TV](https://developers.google.com/tv/web/docs/design_for_tv)
- [The Immoble Web](https://speakerdeck.com/grigs/the-immobile-web)
- [Prince - Convert HTML to PDF with CSS](http://www.princexml.com/)
