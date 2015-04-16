---
group: web-dev-2
playlist: PLWjCJDeWfDde5lA0t6QGVvaqpkqRREe2l
download: https://github.com/acgd-learn-the-web/modular-typography-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/modular-typography-code
---

Creating a modular typography system in CSS creates an extremely reusable font-size system with a harmonious vertical rhythm.

---

## Steps to creating a type system

1. Choose the typeface for the body copy
2. Choose an appropriate font-size; usually 16 px unless the typeface is larger
3. Choose an appropriate line-height for the body text
4. Choose a type scale, often based on a musical or other natural scale
5. Set up the CSS font-sizes, line-heights, and margins to fit the scale

**Example type choices**

- *font-family*: Georgia
- *font-size*: 16px (100%)
- *line-height*: 24px (1.5)
- *type-scale*: 1.125 (major second)

**How to choose a type scale**

- [A List Apart: More Meaningful Typography](http://alistapart.com/article/more-meaningful-typography)
- [24 Ways: Composing the New Canon](http://24ways.org/2011/composing-the-new-canon/)
- [R(a|ela)tional Design](http://blog.8thlight.com/billy-whited/2011/10/28/r-a-ela-tional-design.html)
- [Typographic Scale](http://spencermortensen.com/articles/typographic-scale/)

**Tools**

- <http://type-scale.com/>
- <http://modularscale.com/>
- **[☛ Typografier](http://tjb.io/type)** — A tool I created for myself to generate the default CSS code

---

## CSS for modular typography

I usually start my type-scale with the `h6` set at the same font-size as the body copy, `1rem`, then work upwards from there.

To calculate the font-size there’s just some simple multiplication:

```
font-size: previous-font-size × type-scale
```

So for the `h5`, it would be `1 × 1.125`.

```css
h5 {
	font-size: 1.125rem; /* (1 × 1.125) */
}

h6 {
	font-size: 1rem;
}
```

A more general equation would be this:

```
font-size: base-font-size × type-scale ^ distance-from-base
```

Using the formula to calculate the `h1`:

```css
h1 {
	/* (1 × 1.125 ^ 5) - H1 is 5 steps away from the base font-size */
	font-size: 1.8020rem;
}
```

### Re-usable classes

With a font-size system set to a scale we will want to use those font-sizes outside of `h1` so we should assign classes to them.

Some designers like to use the Greek alphabet for their font-sizes, some like to use the Metric prefixes. I personally prefer the Metric prefixes because they make sense to me and I don’t know whether alpha is my biggest or smallest font-size.

So, we would then assign classes to all the significant font-sizes:

```css
h1,
.exa {
	font-size: 1.8020rem;
}

⋮

h6,
.kilo {
	font-size: 1rem;
}
```

Often we need larger font-sizes (for banners or hero graphics) and smaller font-sizes (for captions or footnotes). So we should make classes that go above and below the heading sizes:

```css
.yotta {
	font-size: 2.2807rem;
}

.zetta {
	font-size: 2.0273rem;
}

⋮

small, .milli {
	font-size: 0.8889rem;
}

.micro {
	font-size: 0.7901rem;
}
```

**Links**

- [Wikipedia: Metric Prefixes](http://en.wikipedia.org/wiki/Metric_prefix)
- [Pragmatic, Practical Font Sizing in CSS](http://csswizardry.com/2012/02/pragmatic-practical-font-sizing-in-css/)

### Vertical rhythm

With our different font-sizes we now need to set everything to a semi-baseline grid—or at least create a harmonious vertical rhythm.

We start by applying a consistent margin to all the typography related elements:

```css
h1, h2, h3, h4, h5, h6,
p, ul, ol, dl, dd, figure
blockquote, details, hr,
fieldset, pre, table {
	margin: 0 0 1.5rem;
}
```

*The margin-bottom is the same size as our line-height.*

Next, we assign a line-height to every font-size in our type-scale that aligns with our base line-height. The idea behind this alignment is create harmony between the text, especially when two columns of text are beside each other—we want the lines of text to align. [Illustrations and explanation here.](http://www.markboulton.co.uk/journal/incremental-leading)

Here’s the formula to calculate the appropriate line-height:

```
line-height: ceil(font-size ÷ base-line-height) × (base-line-height ÷ font-size)
```

To calculate the `h1` it would look like this:

```css
h1, .exa {
	/* line-height: ceil(1.802 ÷ 1.5) × (1.5 ÷ 1.802) */
	font-size: 1.8020rem;
	line-height: 1.6648;
}
```

**Links**

- [Single Direction Margin Declaration](http://csswizardry.com/2012/06/single-direction-margin-declarations/)
- [Mark Boulton: Incremental leading](http://www.markboulton.co.uk/journal/incremental-leading)

#### Re-usable spacers

To keep things consistent throughout our design we want to use a series of consistent bottom margins, usually multiples of the line-height.

So, we can create a series of classes to add consistent margins:

```css
/* Normal, line-height size space */
.push {
	margin-bottom: 1.5rem;
}

/* No space */
.push-none {
	margin-bottom: 0;
}

/* Double normal space */
.push-double {
	margin-bottom: 3rem;
}

/* Half normal space */
.push-half {
	margin-bottom: 0.75rem;
}
```

*We might even want to add a series of classes for consistent paddings for closed in boxes so they can conform to our baseline grid. [Check out the CSS file for a complete series of these classes.](css/typography.css)*

### Adding branding

Often we want a different typeface and colours for the headings, it’s best to separate that into another series of classes for reuse.

```css
h1, h2, h3, h4, h5, h6,
.brand {
	font-family: Helvetica,sans-serif;
	color: #393;
}

.brand-family {
	font-family: Helvetica,sans-serif;
}

.brand-color {
	color: #393;
}
```

Now we can apply these classes to any element to assign them the brand colour or typeface or both.

### Bigger fonts on bigger screens

With responsive sites it’s usually a good idea to increase the font-size on larger screens. This provides the benefit of having larger fonts on screens like televisions.

With a few media queries at the top of our `typography.css` file we can increase sizes incrementally for larger screens.

```css
@media only screen and (min-width: 60em) {

	html {
		font-size: 110%;
	}

}

@media only screen and (min-width: 90em) {

	html {
		font-size: 120%;
	}

}

@media only screen and (min-width: 120em) {

	html {
		font-size: 130%;
	}

}
```

---

## Typography style guide

When starting a new website it’s best to first consider the typography. I generally like to style all the typography related elements to create a mini styleguide.

[⬇ Type styleguide](type-styleguide.html)

**Sample styleguides**

- <http://paulrobertlloyd.com/about/styleguide/>
- <http://barebones.paulrobertlloyd.com/_styleguide.php>
- <http://clearleft.com/styleguide/>

---

## Video list

1. [Modular typography: creating a type scale](https://www.youtube.com/watch?v=dYp7WM8x4uI&list=PLWjCJDeWfDde5lA0t6QGVvaqpkqRREe2l&index=1)
2. [Modular typography: creating reusable classes](https://www.youtube.com/watch?v=AJLPiTIOgAk&list=PLWjCJDeWfDde5lA0t6QGVvaqpkqRREe2l&index=2)
3. [Modular typography: vertical rhythm](https://www.youtube.com/watch?v=sZWLyQwDw7Q&list=PLWjCJDeWfDde5lA0t6QGVvaqpkqRREe2l&index=3)
4. [Modular typography: classes for consistent spacing](https://www.youtube.com/watch?v=FNxwjMcCcBI&list=PLWjCJDeWfDde5lA0t6QGVvaqpkqRREe2l&index=4)
5. [Modular typography: brand fonts and colours](https://www.youtube.com/watch?v=8IZLqReXREY&list=PLWjCJDeWfDde5lA0t6QGVvaqpkqRREe2l&index=5)
6. [Modular typography: examples of use](https://www.youtube.com/watch?v=ZJQi5_te2-I&list=PLWjCJDeWfDde5lA0t6QGVvaqpkqRREe2l&index=6)
7. [Modular typography: bigger fonts on bigger screens](https://www.youtube.com/watch?v=xW7zJKUDl58&index=7&list=PLWjCJDeWfDde5lA0t6QGVvaqpkqRREe2l)
