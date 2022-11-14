---
title: "Using images"
tags: "using images figures captions background foreground url aspect ratio size attachment repeat multiple linear radial repeating gradients sprites replacement hide text patterns border images"
desc: "Different ways to use images in a website including foreground and background images."
playlist: PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7
download: https://github.com/learn-the-web/using-images-code/archive/master.zip
github: https://github.com/learn-the-web/using-images-code
cheatsheet: images-cheat-sheet
extra_practice:
  week:
    title: "Web Dev 3, Week 04"
    url: "/courses/web-dev-3/week-04/"
  slides:
    - title: "Background & retina images"
      url: "/courses/web-dev-3/background-retina-images/"
  activities:
    - title: "Alt attributer"
      url: "alt-attributer"
  lessons:
    - title: "Background images"
      url: "/courses/web-dev-3/background-images/"
  exercises:
    - title: "Leafy decorations"
      url: "/courses/web-dev-3/week-04/#leafy-decorations"
---

Images are a very critical part of modern web design—and there’s lots of different way to use and generate images on websites.

---

## Choosing the right way to insert an image

![](image-choice-flow-chart.png)

1. **Does the image require a caption?**
  <br>*Yes*: Use a `<figure>` & `<figcaption>`.
2. **Is the image an important part of the content?**
  <br>*Yes*: Use an `<img>` tag with an appropriate `alt` attribute.
  <br>*No*: Use a CSS `background-image`.

*Any image that is purely decoration should be in CSS. If that can’t accomplish what you want an `<img>` tag with an empty `alt` attribute will suffice.*

---

## Foreground images

Foreground images, or images inserted into HTML, use the HTML `<img>` tag.

**Use the `<img>` tag when the image is an important part of the content—when the content would be confusing without the image.**

```html
<img src="images/logo.jpg">
<img src="images/icons/planet.jpg">
<img src="../images/photo.jpg">
```

**[☛ Refer to the tutorial on paths](/topics/paths-folders/)**

**Links**

- [MDN: img](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)

### Alt attributes

All images inserted with the `<img>` tag must have an alt attribute:

```html
<img src="pluto.jpg" alt="Photo of Pluto">
```

The alt attribute has two purposes:

1. To describe the photo if it doesn’t download in the browser
2. To describe the photo to someone who cannot see the image, maybe someone using a screen reader

When describing the image you should think about what content is most helpful for a user who cannot see the image. Describe what is important about the image.

- Is the image fancy text? Then just write the word.
- Is it a photo of a planet taken by a telescope? Write something like “Photo of Pluto taken with Hubble”
- Is the photo meant to highlight a point? Write just the point, e.g. “Classic painting showing the triangle composition”
- Is the graphic a chart? Describe the purpose of the chart, e.g. “A bar graph representing the orbital periods of planets in the Solar System”
- Does the graphic not add any relevant information? Then it should be in your CSS. If that’s not possible, leave the `alt` empty, `<img alt="">`

**Links**

- [Simply Accessible: Images in Context](http://simplyaccessible.com/article/images-in-context/)
- [Simply Accessible: Descriptive Alt Attributes](http://simplyaccessible.com/article/descriptive-alt-attributes/)
- [W3: Techniques for providing useful text alternatives](http://dev.w3.org/html5/alt-techniques/)
- [When is an image ‘purely decorative’?](http://www.4syllables.com.au/2014/04/decorative-images/)

### Figures & captions

Often you’ll need to provide a caption for your image, that’s where the `<figure>` element comes in handy.

```html
<figure>
  <img src="pluto.jpg" alt="">
  <figcaption>Photo of Pluto taken with the Hubble Telescope</figcaption>
</figure>
```

Using the `<figure>` and `<figcaption>` elements we can associate a caption with an image.

You’ll notice that the alt attribute is empty in this situation. Often it’s not needed because the content of the caption would be no different than the alt attribute so we don’t want the information repeated.

*Only use the figure element if your image needs a caption, if you don’t need a caption, don’t use the figure.*

**Links**

- [MDN: figure](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure)
- [MDN: figcaption](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figcaption)

---

## Background images

Background images are inserted in CSS and do not use the HTML image tag. **Use background images when the image is purely for decoration.**

Background images can be inserted onto absolutely any HTML element, using the CSS property `background-image`:

```css
body {
  /* Will add a background to the whole page */
  background-image: url("../images/grey-box.png");
}
```

The `url()` function requires you to specify the image in relation to the CSS document. If your CSS file is inside a folder the path will need to exit that folder using `../`.

**[☛ Refer to the tutorial on paths](/topics/paths-folders/)**

**Links**

- [MDN: background-image](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image)
- [CSS-Tricks: background-image](https://css-tricks.com/almanac/properties/b/background-image/)
- [Codrops: background-image](http://tympanus.net/codrops/css_reference/background-image/)

### I can’t see the background image

First, double check that you’ve spelled the file name properly and that the path is correct. *Use the developer tools to confirm the image is loaded by the browser.*

*You will only be able to see the background image if the containing element takes up space on the screen—either by having content or having a height.*

```html
<div></div>
```

```css
div {
  background-image: url("../images/pic.jpg");
}
```

In the scenario above, we wouldn’t see the background image because the `<div>` has no content inside it. Elements that have no content collapse to 0 pixels tall.

We could solve this problem in a few ways:

Put something inside the `<div>`:

```html
<div>
  <h1>Dinosaurs!</h1>
</div>
```

Add a height to the `<div>`—not a very good solution:

```css
div {
  height: 14em;
}
```

Add `padding-top` to the `<div>` to expand it’s dimensions—a good solution for maintaining aspect ratio:

```css
div {
  padding-top: 4em;
}
```

#### Maintaining aspect ratio

If we want the element that has a background image to maintain the aspect ratio of the image we can use `padding-top` in percents. This is a great solution for banner graphics and responsive sites, especially used together with `position: absolute` and `background-size`.

First we have to figure out the percentage for the aspect ratio of our image. Here’s the formula to do that:

```
(image height ÷ image width) × 100
```

As an example, an image with these dimensions: 1920 × 1080

```
(1080 ÷ 1920) × 100 = 56.25
```

So, our CSS would look like this:

```css
div {
  padding-top: 56.25%;
}
```

When used with `background-size` we can scale the element to fit the same aspect ratio of the image.

### Background repeat

By default the background image will try to form a pattern by repeating itself both horizontally and vertically.

![](repeat.png)

To control the patterning effect of the background image you can use `background-repeat`:

- `no-repeat` — shut off repeating, showing the image only once
- `repeat-x` — pattern only horizontally
- `repeat-y` — pattern only vertically
- `repeat` — the default, pattern both horizontally and verticallly

```css
body {
  background-repeat: no-repeat;
}

h1 {
  background-repeat: repeat-x;
}
```

**Links**

- [MDN: background-repeat](https://developer.mozilla.org/en-US/docs/Web/CSS/background-repeat)
- [CSS-Tricks: background-repeat](https://css-tricks.com/almanac/properties/b/background-repeat/)
- [Codrops: background-repeat](http://tympanus.net/codrops/css_reference/background-repeat/)

### Background position

The `background-position` allows us to control where in the element the image is located. We can use keywords, percents, or fixed measurements.

![](position.png)

*When defining `background-position` we must always specify the horizontal & vertical positions—***horizontal first, vertical second.**

- `keywords` — move the the element to specific set points: `top`, `bottom`, `left`, `right`, `center`
- `%` — align the images point at that percentage to the element’s point at that percentage—`keywords` just map to percentages
- `px`, `em`, `rem` — always start in the top-left corner of the image and the element

```css
body {
  background-position: right bottom;
  /* Same as: */
  background-position: 100% 100%;
}

h1 {
  background-position: center top;
  /* Same as: */
  background-position: 50% 0;
}

div {
  background-position: 10px 10px;
}
```

If you want to move the background image a fixed measurement from the bottom or right you can use `calc()`:

![](position-calc.png)

```css
div {
  /* Centered horizontally, 10px up from the bottom */
  background-position: center calc(100% - 10px);
}
```

**Links**

- **[CSS-Tricks: I like how percentage background-position works](https://css-tricks.com/i-like-how-percentage-background-position-works/)**
- [MDN: background-position](https://developer.mozilla.org/en-US/docs/Web/CSS/background-position)
- [CSS-Tricks: background-position](https://css-tricks.com/almanac/properties/b/background-position/)
- [Codrops: background-position](http://tympanus.net/codrops/css_reference/background-position/)
- [Adobe: A Primer To Background Positioning In CSS](http://blogs.adobe.com/dreamweaver/2015/03/a-primer-to-background-positioning-in-css.html)

### Background size

The CSS `background-size` property allows us to scale the image.

![](size.png)

- `cover` — scale the image to fill the whole element
- `contain` — scale the image so all of it is visible in the element
- `auto` — maintain the aspect ratio when scaling
- `%` — scale the image based on the element its inside
- `px`, `em`, `rem` — scale the image to a fixed measurement

**Just like background position we must style first the horizontal size then the vertical size.** Or we can use a couple keywords for scaling.

```css
body {
  /* Scale the image to be 70% the width of the container, figure out the correct height */
  background-size: 70% auto;
}

h1 {
  /* Fill the whole element with the image */
  background-size: cover;
}

div {
  /* Figure out the width, set the height to 200 pixels */
  background-size: auto 200px;
}
```

**Links**

- [MDN: background-size](https://developer.mozilla.org/en-US/docs/Web/CSS/background-size)
- [CSS-Tricks: background-size](https://css-tricks.com/almanac/properties/b/background-size/)
- [Codrops: background-size](http://tympanus.net/codrops/css_reference/background-size/)

### Background attachment

Background attachment allows us to control how the image scrolls: either it scrolls with the page, or stays in place:

- `fixed` — image doesn’t move when scrolling the page
- `scroll` — default, the image moves with the element its inside

```css
body {
  background-attachment: fixed;
}
```

**Links**

- [MDN: background-attachment](https://developer.mozilla.org/en-US/docs/Web/CSS/background-attachment)
- [CSS-Tricks: background-attachment](https://css-tricks.com/almanac/properties/b/background-attachment/)
- [Codrops: background-attachment](http://tympanus.net/codrops/css_reference/background-attachment/)

### Multiple background images

An element can has as many background images as you’d like, just separate each image with a comma:

```css
body {
  background-image: url("grey-box.png"), url("dark-grey-box.png");
}
```

After specifying multiple background images all the other properties can then have commas to control the other images:

```css
body {
  background-size: 100px auto, 75px auto;
  background-position: left top, right top;
  /* One value will apply to all images */
  background-repeat: no-repeat;
}
```

### Gradients

The browser can generate background images for us in the form of gradients: linear, radial, and repeating variants.

#### Linear gradients

Linear gradients are a gradient built in a single direction, we can specify the direction of our gradient as well as many colour stops.

```css
body {
  /* linear-gradient(direction, colour stops…) */
  background-image: linear-gradient(to right, purple, indigo);
}
```

##### Direction

The gradient direction is specified similarly to `background-position`.

![](gradients.png)

- `to left` — completely flat, starting at the right and moving to the left
- `to right bottom` — starting in the left-top corner and moving to the right-bottom
- `to bottom` — straight up and down

The direction can also be written using degrees

- `45deg` — a 45° angled gradient
- `-12deg` — a -13° angled gradient

```css
body {
  background-image: linear-gradient(to left, purple, indigo);
  background-image: linear-gradient(to right bottom, purple, indigo);
  background-image: linear-gradient(45deg, purple, indigo);
}
```

##### Colour stops

With gradients we can specify as many colour stops as we’d like, with of course, a minimum of 2.

Here’s a rainbow gradient:

```css
body {
  background-image: linear-gradient(to right, red, orange, yellow, green, blue, indigo, violet);
}
```

With colour stops we can also specify their position using a value:

```css
body {
  /* This gradient will create a sharp line between red & blue at 40% */
  background-image: linear-gradient(to bottom, red, red 40%, blue 41%, blue);
}
```

#### Radial gradients

Radial gradients are based around an `ellipse` or `circle`, which are the first argument.

```css
body {
  background-image: radial-gradient(circle, green, darkgreen);
}
```

#### Repeating gradients

Repeating gradients both `linear` and `radial` allow us to create simple patterns.

```css
div {
  /* Warning stripes */
  background-image: repeating-linear-gradient(45deg, yellow, yellow 10%, black 10%, black 20%);
}
```

**Links**

- **[Ultimate CSS Gradient Generator](http://www.colorzilla.com/gradient-editor/)**
- [MDN: linear-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient)
- [MDN: radial-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/radial-gradient)
- [MDN: repeating-linear-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/repeating-linear-gradient)
- [MDN: repeating-radial-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/repeating-radial-gradient)
- [Codrops: linear-gradient](http://tympanus.net/codrops/css_reference/linear-gradient/)
- [Codrops: radial-gradient](http://tympanus.net/codrops/css_reference/radial-gradient/)
- [Codrops: repeating-linear-gradient](http://tympanus.net/codrops/css_reference/repeating-linear-gradient/)
- [Codrops: repeating-radial-gradient](http://tympanus.net/codrops/css_reference/repeating-radial-gradient/)

### Shorthand

All of the above background properties can be combined together into a shorthand notation, similar to `font`.

- `background`: `background-image` `background-position` / `background-size` `background-repeat` `background-color`

```css
body {
  background: url("bg.jpg") left top / 100px auto repeat-y red;
}
```

It can even be used with multiple background images:

```css
body {
  background:
    url("grey-box.png") left top / 100px auto no-repeat,
    url("dark-grey-box.png") right top / 75px auto no-repeat,
    linear-gradient(to bottom, transparent, rgba(0,0,0,0,5))
  ;
}
```

*It’s sometimes nice to add each image on its own line for clarity.*

**Links**

- **[Six Revisions: CSS Background Shorthand Property](http://sixrevisions.com/css/background-css-shorthand/)**
- [MDN: background](https://developer.mozilla.org/en-US/docs/Web/CSS/background)
- [CSS-Tricks: background](https://css-tricks.com/almanac/properties/b/background/)
- [Codrops: background](http://tympanus.net/codrops/css_reference/background/)

---

## Sprites

Sprites allow us to combine our images into a single file in Photoshop and using `background-position` show only a single part of the image at a time.

```html
<div class="icon icon-circle"></div>
<div class="icon icon-hex"></div>
<div class="icon icon-star"></div>
```

![](sprites.png)

```css
.icon {
  width: 100px;
  height: 100px;
  background-image: url("icons.png");
  background-repeat: no-repeat;
}

.icon-circle {
  background-position: 0 0;
}

.icon-hex {
  background-position: 0 -100px;
}

.icon-star {
  background-position: 0 -200px;
}
```

We adjust the position of the background image to only show a portion of it in the element—kind of like a clipping mask.

### Changing images on hover

The best way to change images when you hover is to use sprites: create a sprite with both the default and the hover versions of the images, then just apply some CSS.

```css
.star {
  display: inline-block;
  width: 50px;
  height: 50px;
  background: transparent url("../images/star.svg") no-repeat 0 0;
}

.star:hover {
  /* Change the background position on hover */
  background-position: 0 -50px;
}
```

The trick is to just adjust the background position when the user hovers over the element.

**Links**

- [CSS-Tricks: CSS Sprites](https://css-tricks.com/css-sprites/)
- [CSS-Tricks: Icon System with SVG Sprites](https://css-tricks.com/svg-sprites-use-better-icon-fonts/)

---

## Image replacement

Image replacement is a technique to replace text on the page with an image in an accessible manner.

The technique is useful when you cannot produce the text style you’d like in CSS.

```html
<h1 class="masthead ir">Rainbows</h1>
```

```css
.ir {
  /* The technique pushes the text off the side of the element and chops it off */
  overflow: hidden;
  text-indent: 100%;
  white-space: nowrap;
}

.masthead {
  background: url("rainbow.jpg") left top no-repeat transparent;
  /* Put a min-height on the element equal to the image’s height */
  min-height: 100px;
}
```

**Links**

- [Zeldman: New Image Replacement](http://www.zeldman.com/2012/03/01/replacing-the-9999px-hack-new-image-replacement/)

---

## Patterns

Patterns are simple to use in CSS because of the `background-repeat` property, but not always the easiest to set up. [Check out the video where I debug a pattern](https://www.youtube.com/watch?v=M4M1HT-Tlxs&index=9&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7).

**Links**

- [Subtle Patterns](http://subtlepatterns.com/)
- [Patternify](http://www.patternify.com/)

---

## Border images

Border images allow us to slice an image into 9 pieces and use those pieces on a border instead of the built-in border styles.

### Slicing an image into 9 pieces

The first thing to think about when creating a border image is that it will be sliced into 9 different pieces to be used in different locations in the border.

Here’s an example of a 9-sliced image:

![](border-image.svg)

The grid patterns creates 9 different pieces out of the image:

1. The top-left corner
2. The top-centre edge
3. The top-right corner
4. The right-centre edge
5. The bottom-right corner
6. The bottom-centre edge
7. The bottom-left corner
8. The left-centre edge
9. The centre—which isn’t used anywhere

Now that we can see how the image is sliced we can insert it into the border.

### Inserting the image into the border

It’s often best to first put a standard border when using border-image, as a fallback in-case the image doesn’t download.

Then we add a property to define the `border-image` itself.

```css
.box {
  border: 36px solid purple;
  border-image: url("../images/border-image.svg") 36px;
}
```

The `36px` part in both the `border` and `border-image` is important: it maps to the slices of the image. In the above image there’s a simple slice: equal `36px` on every side.

But we could slice the image 4 times, and use 4 different numbers:

```css
.box {
  border-image-slice: 12px 14px 16px 18px;
}
```

If we specify 4 numbers we are cutting the image this way:

- `12px` down from the top
- `14px` in from the right
- `16px` up from the bottom
- `18px` in from the left

### Gradient as a border image

One fun addition to border images is that we can use gradients because they are just images generated by the browser.

```css
.unicorn-btn {
  border: 4px solid magenta;
  border-image-source: linear-gradient(to right, red, orange, yellow, green, blue, indigo, violet);
  border-image-slice: 1;
}
```

This will produce and *amazing* rainbow gradient that goes from left to right around the edge of the button.

**Links**

- **[CSS-Tricks: Understanding border-image](https://css-tricks.com/understanding-border-image/)**
- [Border image generator](https://developer.mozilla.org/en-US/docs/Web/CSS/Tools/Border-image_generator)
- [MDN: border-image](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image)
- [Code It Down: Border image](http://codeitdown.com/css/css-border-image/)

---

## Video list

1. [Using images: HTML image tags](https://www.youtube.com/watch?v=xVv3SHU_l1o&index=1&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7)
2. [Using images: alt attributes](https://www.youtube.com/watch?v=xcWwcTRS79s&index=2&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7)
3. [Using images: figures](https://www.youtube.com/watch?v=X-uIMl8V6kg&index=3&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7)
4. [Using images: background images](https://www.youtube.com/watch?v=pF-AeeBIvzo&index=4&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7)
5. [Using images: multiple background images](https://www.youtube.com/watch?v=dt6Af0V-Xxw&index=5&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7)
6. [Using images: gradients](https://www.youtube.com/watch?v=d6cYf6qXHBQ&index=6&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7)
7. [Using images: CSS sprites](https://www.youtube.com/watch?v=nm8D1tTs5bY&index=7&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7)
8. [Using images: changing image on hover](https://www.youtube.com/watch?v=zoLaoLGblzc&index=8&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7)
9. [Using images: image replacement](https://www.youtube.com/watch?v=U7B9-UtEK7w&index=9&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7)
10. [Using images: patterns](https://www.youtube.com/watch?v=Oo1FhkvshRo&index=10&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7)
11. [Using images: border images](https://www.youtube.com/watch?v=NL0jcXvm454&index=11&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7)
12. [Using images: gradient border image](https://www.youtube.com/watch?v=EjuXJ0TsXQk&index=12&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7)
13. [Using images: creating a button](https://www.youtube.com/watch?v=pIDLkglb_WE&index=13&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7)
14. [Using images: hero banner with background images](https://www.youtube.com/watch?v=RBxtA5ZM1MY&index=14&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7)
15. [Using images: improving the toggle nav](https://www.youtube.com/watch?v=B15cheIlUZ0&index=15&list=PLWjCJDeWfDdewUQe57s3Tuktg_8eT0yA7)
