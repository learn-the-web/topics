---
title: "JavaScript effects"
tags: "javascript effects scrolling transitions animations end events waypoints smooth scroll manipulating svg"
desc: "Using JavaScript to trigger and create lots of effects on a website like animations and scrolling effects."
playlist: PLWjCJDeWfDdfAAbxA-H5XHQlGoLICyHe_
download: https://github.com/acgd-learn-the-web/javascript-effects-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/javascript-effects-code
---

Common JavaScript effects used on websites: triggering animations, scrolling effects, smooth scrolling, and waypoints.

---

## Triggering CSS animations

CSS animations can be triggered by JavaScript simply by storing the `animation` property in a class.

```css
.box {
  /* What ever properties here, just not `animation` */
}

.js-animate {
  animation: do-stuff 200ms linear;
}

@keyframes do-stuff {
  ⋮
}
```

In our JavaScript all we have to do is assign the appropriate class to the element:

```js
var $box = $('.box');

$box.addClass('js-animate');
```

If we try to trigger the animation again by re-adding the class the animation won’t work—because the class is already there.

If we remove the animation class the animation stops immediately, but after the class has been removed we can add the class again to trigger the animation.

### Triggering transitions

We can also trigger transitions by setting them up in the default state for the element, then when its properties change, the transition will automatically trigger.

```css
.box {
  opacity: 0;
  transition: all 200ms linear;
}

.js-box-fade {
  opacity: 1;
}
```

All the JavaScript needs to do is add the `js-box-fade` class, then the `transition` will just automatically trigger.

### Listening for animations to end

Sometimes it’s helpful to listen for when the animation completes—this is a good place to remove the class from the element.

```js
var $box = $('.box');

$box.on('animationend', function () {
  // This function will execute when the animation ends
  // Would be a good place to remove the class from the element
});
```

We probably need to worry about vendor prefixes in the above code, the same as when creating keyframes.

```js
var $box = $('.box');

$box.on('webkitAnimationEnd animationend', function () {
  // Notice the `webkitAnimationEnd` above
  // The vendor prefixed version of the event and the original will be listened to
});
```

### Transition end

We can, of course, also listen for transition end, with the `transitionend` event. The JavaScript code is exactly the same as for animations:

```js
var $box = $('.box');

$box.on('transitionend', function () {

});
```

**Links**

- [MDN: transitionend](https://developer.mozilla.org/en-US/docs/Web/Events/transitionend)
- [MDN: animationend](https://developer.mozilla.org/en-US/docs/Web/Events/animationend)
- [Animating List Items](https://cssanimation.rocks/list-items/)
- [Animate.css](http://daneden.github.io/animate.css/)

### JavaScript animation libraries

For more complex animations and interactions there’s a bunch of JavaScript libraries to help out.

- **[GSAP](http://greensock.com/gsap)**
- [Velocity.js](http://julian.com/research/velocity/)
- [Textillate.js](http://jschr.github.io/textillate/)

---

## Scrolling animations

With JavaScript we can detect lots of things happening to the browser, specifically what happens to the window.

The browser window fires a bunch of events that we can listen to. The ones I use most often are `resize` and `scroll`.

```js
var $win = $(window);

$win.on('scroll', function () {
  // This event will be fired every time the browser scrolls
});
```

Using a property of the the window: `scrollTop`, we can figure out how far from the top the browser has scrolled.

```js
var $win = $(window);

$win.on('scroll', function () {
  // Will give use a number, in pixels, that the browser has scrolled down
  var topPixels = $win.scrollTop();
});
```

We can use the `scrollTop` number to manipulate elements on the page, like rotate them, etc.

### Waypoints

Using waypoints we can trigger something when the browser scrolls to a specific location. It is much easier if we use the [jQuery Waypoints](http://imakewebthings.com/waypoints/) plugin.

```html
⋮
<img class="thing" src="#" alt="">
⋮
```

If this `img` is further down the page, we can use Waypoints to do something to it at a specific point in time.

First include that script on your page, either by downloading it or using a content delivery network like [cdnjs](https://cdnjs.com/).

```html
  <script src="js/jquery.min.js"></script>
  <!-- It's important that Waypoints comes after jQuery because it depends on jQuery to function -->
  <script src="js/jquery.waypoints.min.js"></script>
  <script src="js/main.js"></script>
</body>
</html>
```

In our JavaScript we can now detect when an element scrolls to the top of the page.

```js
var $img = $('.thing');

$img.waypoint(function () {
  // Code will be executed when the image reaches the top of the screen
});
```

#### Waypoint offsets

If we want to execute the function before the element reaches the top, we can use an offset:

```js
var $img = $('.thing');

$img.waypoint(function () {
  // Executed when the image reaches halfway up
}, { offset: '50%' });
```

Notice the `offset` on the last line of code, with `50%` the element would be halfway up the screen for the function to execute.

#### Waypoint direction

We can also detect whether the browser is scrolling up or down using Waypoints.

The function callback will pass an argument that includes the direction the browser is traveling—we just have to capture it.

```js
var $img = $('.thing');

$img.waypoint(function (direction) {
  if (direction == 'down') {
    // Do something when scrolling down
  }

  if (direction == 'up') {
    // Do something when scrolling up
  }
}, { offset: '50%' });
```

#### Waypoints and parallax

If we want to use Waypoints and [**☛ CSS Parallax**](/topics/css-animations-effects/#parallax) together, there’s just a few minor changes we have to make.

First, the `body` can’t be the scrollable element, for better browser support. We need to wrap the whole website in a `div`:

```html
<div class="wrapper">
  <!-- Whole website goes in here -->
</div>
```

Then, we move all the scrollbar stuff from `body` onto this `div`:

```css
body {
  margin: 0;
  overflow: hidden;
}

.wrapper {
  height: 100vh;
  overflow-y: auto;
  overflow-x: hidden;
  -webkit-overflow-scrolling: touch;

  -webkit-perspective: 1px;
  perspective: 1px;
}
```

Finally, we just have to change the `context` that Waypoints uses to monitor scrolling on to our new `div`:

```js
var $img = $('.thing');

$img.waypoint(function () {
  // JavaScript stuff here
}, { context: '.wrapper' }); // Change the context to `.wrapper`
```

And that’s it: our waypoints and CSS parallax should work together!

**Links**

- [jQuery Waypoints](http://imakewebthings.com/waypoints/)

---

## Smooth scroll

A very common pattern in websites is smooth scrolling: when you click on the top navigation the browser slowly animates down to the appropriate section.

The most reliable plugin I’ve found to do that is [LocalScroll by Ariel Flesler](http://flesler.blogspot.ca/2007/10/jquerylocalscroll-10.html).

First include the LocalScroll plugin and its companion ScrollTo—order is important. *Either download it to your website or use a CDN.*

```html
  <!-- Must come first -->
  <script src="js/jquery.min.js"></script>
  <!-- Must come after jQuery because it uses jQuery -->
  <script src="js/jquery.scrollTo.min.js"></script>
  <!-- Must come after ScrollTo because it uses ScrollTo -->
  <script src="js/jquery.localScroll.min.js"></script>
  <!-- Must come last because our code needs all the above scripts -->
  <script src="js/main.js"></script>
</body>
</html>
```

The HTML setup is no different than normal HTML with internal links:

```html
<ul class="nav">
  <li><a href="#plant-eaters">Plant Eaters</a></li>
  <li><a href="#meat-eaters">Meat Eaters</a></li>
</ul>

<section id="plant-eaters"></section>

<section id="meat-eaters"></section>
```

In our JavaScript, we only need one line of code:

```js
$('.nav').localScroll();
```

*It’s important that when using LocalScroll you target the parent that includes all the `<a>` tags—not the `<a>` tag directly. Targeting the link directly won’t work with LocalScroll.*

### Smooth scroll and parallax

If we want to use smooth scrolling and [**☛ CSS Parallax**](/topics/css-animations-effects/#parallax) together, there’s just a few minor changes we have to make.

In our JavaScript we have to target a new element as the scrollable:

```js
$('.nav').localScroll({
  target: '.wrapper' // Or just 'body' if we’re not also using Waypoints
});
```

**Links**

- [LocalScroll](http://flesler.blogspot.ca/2007/10/jquerylocalscroll-10.html)
- [ScrollTo](http://flesler.blogspot.ca/2007/10/jqueryscrollto.html)

---

## Manipulating SVG

With our SVG embedded directly in HTML we can treat the elements like any other HTML element and manipulate them with JavaScript.

```xml
<div class="graphic">
  <svg width="256" height="256" viewBox="0 0 256 256" version="1.1" xmlns="http://www.w3.org/2000/svg">
    <rect class="my-rect" x="10" y="10" width="75" height="50" />
  </svg>
</div>
```

Then, in JavaScript, we can select and manipulate the elements. Here’s an example with jQuery:

```js
var $myRect = $('.my-rect');
$myRect.css('fill', '#000');
```

### Triggering SVG animations & transitions

Since we can apply transitions and animations to our SVGs, we can also trigger them using JavaScript.

First we need to set up our CSS, something like this:

```css
.js-bounce {
  animation: bounce 1s linear;
}

@keyframes bounce {

  0% {
    top: 0;
  }

  100% {
    top: 100px;
  }

}
```

Then, just trigger it with `addClass`:

```js
var $graphic = $('.graphic');
$graphic.addClass('js-bounce')
```

We could also do it with a waypoint:

```js
var $graphic = $('.graphic');

$graphic.waypoint(function () {
  $graphic.addClass('js-bounce');
});
```

We can do exactly the same thing with transitions, treating SVG no differently than standard HTML elements.

### SVG manipulation libraries

For more complex SVG animations and manipulations there’s a bunch of JavaScript libraries to help out.

- **[Snap.svg](http://snapsvg.io/)**
- [SVG.js](http://www.svgjs.com/)
- [Vivus](http://maxwellito.github.io/vivus/)
- [Transforms on SVG Elements](https://css-tricks.com/transforms-on-svg-elements/)

---

## Video list

1. [JavaScript effects: triggering animations](https://www.youtube.com/watch?v=8NcbPhLulas&index=1&list=PLWjCJDeWfDdfAAbxA-H5XHQlGoLICyHe_)
2. [JavaScript effects: listening for the animation to end](https://www.youtube.com/watch?v=Ja0YxV-DCsE&index=2&list=PLWjCJDeWfDdfAAbxA-H5XHQlGoLICyHe_)
3. [JavaScript effects: scrolling animations](https://www.youtube.com/watch?v=nhHqiGCG10E&index=3&list=PLWjCJDeWfDdfAAbxA-H5XHQlGoLICyHe_)
4. [JavaScript effects: waypoints](https://www.youtube.com/watch?v=5hPVpVtgle4&index=4&list=PLWjCJDeWfDdfAAbxA-H5XHQlGoLICyHe_)
5. [JavaScript effects: smooth scrolling](https://www.youtube.com/watch?v=OkmwkrSEBMo&index=5&list=PLWjCJDeWfDdfAAbxA-H5XHQlGoLICyHe_)
6. [JavaScript effects: trigger animations & transitions on SVGs](https://www.youtube.com/watch?v=HFdvTWVBplA&index=6&list=PLWjCJDeWfDdfAAbxA-H5XHQlGoLICyHe_)

## Supplemental links

- [cdnjs](https://cdnjs.com/)
