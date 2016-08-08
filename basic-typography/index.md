---
playlist: PLWjCJDeWfDdcZadRkkeuz1NYSJ0phrstG
download: https://github.com/acgd-learn-the-web/basic-typography-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/basic-typography-code
cheatsheet: web-typography-cheat-sheet
---

CSS provides lots of control over typography on your website—here’s some of the basics.

---

## Styling the font

When styling the font in CSS there’s a bunch of properties we can use to control the style.

### Font family

The `font-family` property is used to style the typeface used in your website.

Most computers have a few default fonts that we can almost guarantee to be there: Arial, Verdana, Georgia, Courier, Times New Roman, Comic Sans, and maybe a few more.

```css
html {
  font-family: Georgia;
}
```

The above property will change all the text in the website to Georgia—assuming it’s installed on the computer—because we’ve targeted the `html` element.

We really can’t guarantee that Georgia will be installed on the person’s computer, so it’s a good idea to provide a stylistic backup: `serif`, `sans-serif`, `monospace`, `cursive`.

```css
html {
  /* Try to load Georgia, if it doesn't exist load another serif font */
  font-family: Georgia, serif;
}
```

When specifying a font family that has a space in its name we must surround it with quotes:

```css
html {
  font-family: "Comic Sans MS", sans-serif;
}
```

**Links**

- [Common fonts to all versions of Windows & Mac equivalents](http://www.ampsoft.net/webdesign-l/WindowsMacFonts.html)

### Font properties

Here’s a bunch of other font properties we can use to adjust our typography.

```css
h1 {
  font-size: 2rem;
  font-weight: bold;
  font-style: italic;

  /*
    On the web a loose line-height has been shown to be more readable
    1.5 is good for body copy
  */
  line-height: 1.5;
}
```

- `font-size` — for adjusting the size of the font: a single number with a unit (`rem` [the best choice], `em`, `px`)
- `font-weight` — for adjusting the boldness: `bold` or `normal`
- `font-style` — for adjusting the italics: `italic` or `normal`
- `line-height` — for adjusting the line-height: a single number, a multiplier that multiplies the font-size

### Font shorthand

For fonts, we can actually specify a bunch of CSS properties on a single line in a more compact manner, called shorthand.

```css
html {
  /* font: font-style (optional) font-weight font-size/line-height font-family; */
  font: normal 1rem/1.5 Georgia, serif;
}
```

### Text decorations

There are a bunch of decorative things we can do to our text.

```css
p {
  text-transform: uppercase;
  text-decoration: line-through;
  text-align: center;
  text-indent: 1em;

  /* text-shadow: horizontal-offset vertical-offset blur-radius colour */
  text-shadow: 2px -4px 6px red;
}
```

- `text-transform` — change capitalization: `uppercase`, `lowercase`, `capitalize`
  It’s a good idea to use CSS to make all caps instead of writing it directly in HTML for accessibility reasons.
- `text-decoration` — add line-decorations: `none`, `underline`, `line-through`, `overline`
  The only things in a website that should be underlined are links.
- `text-align` — alignment of the text: `left`, `center` (American spelling), `right`, `justify`
- `text-indent` — indent the first line of text like traditionally printed materials
- `text-shadow` — adding a shadow to the text: specified like this: `text-shadow: horizontal-offset vertical-offset blur-radius colour`

### Font sizing units: rem vs. em vs. px

There are lost of different units to use while choosing a font-size—pixels are the easiest to understand but not the most accessible for users.

One important fact to remember about designing on the web is that many things are just recommendations—especially font sizes. Browsers provide a way for users to adjust the default font size of text: if users prefer bigger fonts they can change it, if users prefer smaller fonts they can change it.

Setting our font-sizes in pixels takes away control from our users. If our users have poor vision they can no longer enlarge their font size.

Rems and ems are a great solution that allow relative font sizes. They are basically multipliers on top of the base font size set in the browser.

- `2rem` means: “take the default font size and multiply it by 2, making it bigger”
- `0.5rem` means: “take the default font size and multiply it by 0.5, making it smaller”

#### Rem vs. em

- The `rem` unit is always based on the font-size of the `html` element
- The `em` unit is always based on the font-size of the parent element

```html
<p>Some text.</p>

<div>
  <p>Some inner text.</p>
</div>
```

1. If we set `font-size: 2em` on the `p` tag by default they’ll both be the same: calculated as `base-font-size × 2`
2. If we then set `font-size: 3rem` on the `div`, the inner `p` tag will now be different, larger: `base-font-size × 3 (from the div) × 2`
3. But if I change the font size on all `p` tags to `2rem` then the inner `p` tag will be exactly `2rem` and will not compound on the parent’s font size.

*So, overall, I usually use `rem` when sizing fonts because it’s the easiest to keep consistent.*

---

## Styling links

Styling links in websites is not really different from other elements, but they must be styled directly, and don’t inherit certain properties from their parent elements.

```css
a {
  color: darkgreen;

  /*
    Be careful when removing the underline from links
    Make sure there is still enough contrast to understand the text as a link
  */
  text-decoration: none;
}
```

Links have a bunch of states that we can also style when a user interacts.

```css
a,
a:link {
  color: darkgreen;
}

a:visited {
  color: limegreen;
}

a:hover {
  color: orange;
}

a:focus {
  color: blue;
}

a:active {
  color: red;
}
```

- `:link` — for styling the default link state
- `:visited` — for styling the link after it’s been visited by the user
- `:hover` — for styling the link when the mouse is sitting over it
- `:focus` — for styling the link when the keyboard has tab-focused it
- `:active` — for styling the link when the mouse button is pressed down on it

*It’s important that these link states go in this direction: link, visited, hover, focus, active. There’s a fun a mnemonic to remember the order: “Lord Vader’s Handle Formerly Anakin”.*

**Links**

- [Six Revisions: CSS Link Pseudo-classes](http://sixrevisions.com/css/link-pseudo-classes/)

---

## Styling lists

When we create lists in HTML the brower applies default CSS to them:

- For `ul` lists we get bullets
- For `ol` lists we get numbers

But, those are just the defaults and we can completely overwrite those bullets and numbers with the `list-style-type` property.

```css
ul, ol {
  list-style-type: decimal; /* Simple numbers (1, 2, 3, etc.) */
  list-style-type: lower-alpha; /* Lowercase letters (a, b, c, d, etc.) */
  list-style-type: lower-roman; /* Lowercase Roman numerals (i, ii, iii, etc.) */
  list-style-type: lower-greek; /* Lowercase Greek letters (α, β, ɣ, etc.) */
  list-style-type: disc; /* The default filled bullet (•)*/
  list-style-type: circle; /* Add empty circle bullets (◦) */
  list-style-type: square; /* Add square shaped bullets (■) */
  list-style-type: none; /* Remove all bullets and numbers */
}
```

**Links**

- [MDN: list-style-type](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)

---

## Web fonts and custom typefaces

Beyond the core web fonts for font family we can use custom typefaces that get downloaded to our computers and used to display the website.

*The fonts must be properly licensed for the web—the ones installed currently on your computer are not.*

There are lots of different services for Web Fonts—Google Fonts is a simple one to start with and uses open fonts that are licensed for any situation.

**[☛ Follow this tutorial to see how to use Google Fonts](/topics/google-fonts/)**

**Links**

- **[Google Fonts](http://www.google.com/fonts)**
- **[Font Squirrel](http://www.fontsquirrel.com/)** — has a great font generator and packaging tool
- [Adobe Typekit](https://typekit.com/)

---

## Video list

1. [Basic typography: family and size](https://www.youtube.com/watch?v=BuL2GjDx9fA&list=PLWjCJDeWfDdcZadRkkeuz1NYSJ0phrstG&index=1)
2. [Basic typography: weight, style, line height](https://www.youtube.com/watch?v=eirNBsaxLZ8&list=PLWjCJDeWfDdcZadRkkeuz1NYSJ0phrstG&index=2)
3. [Basic typography: font shorthand](https://www.youtube.com/watch?v=sas2NtB4FQo&list=PLWjCJDeWfDdcZadRkkeuz1NYSJ0phrstG&index=3)
4. [Basic typography: rem vs. em vs. px](https://www.youtube.com/watch?v=vy-lRUMpEOs&list=PLWjCJDeWfDdcZadRkkeuz1NYSJ0phrstG&index=4)
5. [Basic typography: decorative text](https://www.youtube.com/watch?v=JO6J2ta9isE&list=PLWjCJDeWfDdcZadRkkeuz1NYSJ0phrstG&index=5)
6. [Basic typography: styling links](https://www.youtube.com/watch?v=8JKPUPSJ-G8&list=PLWjCJDeWfDdcZadRkkeuz1NYSJ0phrstG&index=6)
7. [Basic typography: styling lists](https://www.youtube.com/watch?v=gYZ2jflYozI&list=PLWjCJDeWfDdcZadRkkeuz1NYSJ0phrstG&index=7)
8. [Basic typography: custom typefaces with web fonts](https://www.youtube.com/watch?v=mmu44j4PoqQ&list=PLWjCJDeWfDdcZadRkkeuz1NYSJ0phrstG&index=8)

## Supplemental links

- **[Five simple steps to better typography](http://www.markboulton.co.uk/journal/five-simple-steps-to-better-typography)**
- **[The State of Web Type](http://stateofwebtype.com/)**
- [The Elements of Typographic Style Applied to the Web](http://webtypography.net/)
- [CSS Typography: The Basics](http://sixrevisions.com/css/css-typography-01/)
- [Common fonts to all versions of Windows & Mac equivalents](http://www.ampsoft.net/webdesign-l/WindowsMacFonts.html)
- [Text-rendering: optimizeLegibility is Decadent and Depraved](http://bocoup.com/weblog/text-rendering/)
- [Web Font Test](http://webfont-test.com/)
- [Mind Your En And Em Dashes: Typographic Etiquette](http://www.smashingmagazine.com/2011/08/mind-your-en-and-em-dashes-typographic-etiquette/)
