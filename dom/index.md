---
playlist: PLWjCJDeWfDdexVfek9nZEdmbyBL6_yP6Y
download: https://github.com/acgd-learn-the-web/dom-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/dom-code
cheatsheet: javascript-cheat-sheet
checklist: javascript-checklist
---

The DOM—Document Object Model—is the system that Javascript uses to interact with HTML. The DOM is really Javascript’s representation of your HTML document that can be fully manipulated.

---

## Plain Javascript vs. jQuery

With Javascript in the browser, Javascript’s primary purpose is to manipulate HTML, respond to user events, and manage data.

You can use either plain Javascript or jQuery with you’re developing your website. jQuery doesn’t replace Javascript, you’ll still end up using all of your Javascript knowledge, jQuery just extends and simplifies some of the Javascript tasks.

### Including jQuery

jQuery is simple to use on your website, you just have to include the jQuery Javascript file and you’ll inherit all of jQuery’s functionality.

1. You can download the jQuery file from the website and put it in your `js` folder
2. You can use a content delivery network, CDN, to include jQuery

```html
  <!-- Using the downloaded version of jQuery -->
  <script src="js/jquery.min.js"></script>
  <script src="js/main.js"></script>
</body>
</html>
```

*Make sure you put jQuery before your own Javascript file.*

**Links**

- [jQuery](http://jquery.com/)

---

## Selecting HTML elements

Since much of what you want to do with Javascript is manipulate HTML, you first need to select the elements using Javascript.

Selecting elements in Javascript is really simple if you know how to select things in CSS—it uses the exact same selector system.

*It’s helpful, when beginning, to pick one method, plain JS or jQuery, when selecting HTML elements.*

### Selecting with plain JS

There are a bunch of different functions for selecting things in plain Javascript.

- `document.getElementById('thing')` — will select an element with the id of `thing`
- `document.getElementsByTagName('div')` — select all the `div` elements on the page
- `document.getElementsByClassName('thang')` — select all the elements with the class of `thang`
- `document.querySelector('.thang')` — will select the first element with the class of `thang`; you can put any CSS selector in there and it will work
- `document.querySelectorAll('.thang')` — will select all the elements with the class of `thang`; you can put any CSS selector in there and it will work

Here’s a couple of examples:

```html
<h1>Heading Level 1</h1>
<div class="thang">
  <p>Text and text and stuff and junk.</p>
  <p class="thing">Lots more texty text stuff.</p>
</div>
```

When selecting things in Javascript it’s a good idea to put the selection into a variable because selecting things causes a performance hit, while reading a variable is fast.

```js
// Get the single <h1>
var theH1 = document.querySelector('h1');
// Get all the <p> tags
var thePTags = document.querySelectorAll('p');
// Get the element with the class of thing
var thing = document.querySelector('.thing');
```

#### Looping over collections in plain JS

When selecting a bunch of elements with `querySelectorAll()`, if you want to manipulate all of them, you’ll have to loop over all elements.

```js
var thePTags = document.querySelectorAll('p');
var i;

for (i = 0; i < thePTags.length; i++) {
  thePTags[i].style.color = 'red';
}
```

**Links**

- [MDN: document.querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/document.querySelector)
- [MDN: document.querySelectorAll()](https://developer.mozilla.org/en-US/docs/Web/API/document.querySelectorAll)
- [CSS Tricks: Loop querySelectorAll matches](http://css-tricks.com/snippets/javascript/loop-queryselectorall-matches/)

### Selecting with jQuery

With jQuery, selecting things is the same as plain Javascript: it uses CSS selectors.

*If you select something using plain JS, you can’t use jQuery functions without selecting it with jQuery. If you select something with jQuery, you can’t use plain JS functions.*

- `$('#thing')` — will select an element with the ID of `thing`
- `$('div')` — select all the `div` elements on the page
- `$('.thang')` — will select all the elements with the class of `thang`

#### Looping over collections in jQuery

If you want to apply something to all the elements you selected in jQuery, there are two ways to do it:

1. Directly using the collection
2. Using a loop

```js
var $thePTags = $('p');

// Directly: this will apply the same CSS to all the elements
$thePTags.css('color', 'red');

// A loop
$thePTags.each(function (i) {
  // $(this) refers the current thing inside this loop
  $(this).css('color', 'red');
});
```

*When naming variables in Javascript that contain jQuery objects and collections, it’s common convention to start their name with a `$`.*

**Links**

- [jQuery: Selecting elements](http://learn.jquery.com/using-jquery-core/selecting-elements/)
- [jQuery: Selectors](http://api.jquery.com/category/selectors/)
- [jQuery: .each()](http://api.jquery.com/each/)

---

## Listening to events

When writing Javascript, responding to events is a big part of what your code does. Your code can either respond to user-triggered events or browser-triggered events.

### Events in plain JS

After selecting an element in Javascript we can listen to events on that element, like a click.

```js
var btn = document.querySelector('.btn');

btn.addEventListener('click', function () {
  // All the code here will be executed on every click
});
```

#### The event object

When an event function is executed, Javascript passes an argument to the function called the `EventObject`.

The EventObject houses a bunch of important functions and information about the event that was just executed.

```js
var btn = document.querySelector('.btn');

btn.addEventListener('click', function (e) {
  // Capture the EventObject into the argument named `e`
  e.target; // A reference to the element the event fired on
});
```

### Events in jQuery

Listening to events in jQuery is basically the same, just with a little bit less code:

```js
var $btn = $('.btn');

$btn.on('click', function () {
  // All the code here will be executed on every click
});
```

We could also listen to other events, like key presses:

```js
$('html').on('keydown', function (e) {
  // The number representing the key that was pressed
  console.log(e.keyCode);
});
```

### Event propagation

Events follow a propagation in Javascript that includes the capture phase: starting at the `<html>` element and working down the children until it hits the element; then the bubbling phase that goes backwards up the parents of the element. *On each element in the capturing and bubbling phase an event is fired.*

**Capturing phase:**

```html
<html> <!-- 1. Event will fire here first -->
  <body> <!-- 2. Then here -->
    <div> <!-- 3. And here -->
      <a> <!-- 4. Finally the event will fire on the element you're listening to -->
```

**Bubbling phase:**

```html
<html> <!-- 4. Finally ending here -->
  <body> <!-- 3. Then here -->
    <div> <!-- 2. Then it will traverse up to the the parent -->
      <a> <!-- 1. The event already fired here -->
```

We can control the capturing & bubbling of events using a few functions.

```js
$('a').on('click', function (e) {
  // Will stop the element from doing what it normally does
  e.preventDefault();
  // Will stop the event bubbling back up through its parents
  e.stopImmediatePropagation();
});
```

*Using `e.preventDefault()` on `<a>` tags will stop the browser from navigating to another page.*

### Event delegation

Sometimes we need to capture events on elements that don’t exist yet, or when there’s lots and lots of elements where binding listeners to all of them would be a performance issue.

For this we can use event delegation.

```html
<ul class="dinos">
  <li>Stegosaurus</li>
  <li>Tyrannosaurus</li>
  <li>Apatosaurus</li>
</ul>
```

With this HTML we can bind our event to the `<ul>` itself, but then only listen for events that fire on the `<li>` elements.

```js
$('.dinos').on('click', 'li', function () {
  // Notice the `li` above indicating the delegated element
});
```

**Links**

- [Learn jQuery: Events](http://learn.jquery.com/events/)

---

## Manipulating classes

When manipulating CSS from Javascript it’s very easy to just add the styles directly into the CSS. But from a maintainability & collaboration perspective it’s good to not cross the streams: keep HTML in HTML, CSS in CSS, and only JS in JS.

It’s best practice to just add and remove classes on elements: CSS classes are the contract between your Javascript and your HTML/CSS. *The CSS can deal only with styling and the JS only deals with activating that CSS.*

### Naming conventions

When using classes specifically for Javascript it’s best practice to prepend them with `js-`, so everybody is clear on their purpose.

```css
.js-active {
  display: block;
}

.js-highlight {
  background-color: #ff3;
}
```

### Class manipulation with plain JS

There are two ways to manipulate classes in plain Javascript: `className` and `classList`. Using `className` is more direct and will work in every browser, but isn’t convenient. Using `classList` is much simpler but is only supported in newer browsers.

`className` is a string that represents all the contents of the `class=""` attribute—so we need to manipulate it like a standard string.

```js
var btn = document.querySelector('.btn');

// Add a class: you have to use `+=` because `className` is just a string
btn.className += ' js-highlight'; // Make sure there's a space between this class and the previous
// Remove a class: because `className` is just a string we need to use `replace()`
btn.className.replace('js-highlight', '');
```

`classList` is newer and far more convenient to use.

```js
var btn = document.querySelector('.btn');

// Add a class with `add()`
btn.classList.add('js-highlight');
// Remove a class with `remove()`
btn.classList.remove('js-highlight');
// Toggle a class on/off with `toggle()`
btn.classList.toggle('js-highlight');
// Check to see if the element has a class
btn.classList.contains('js-highlight');
```

**Links**

- [MDN: classList](https://developer.mozilla.org/en-US/docs/Web/API/Element.classList)

### Class manipulation with jQuery

Class manipulation in jQuery is very similar to `classList`, in fact `classList` as inspired by jQuery and other Javascript libraries.

```js
var $btn = $('.btn');

// Add a class with `addClass()`
$btn.addClass('js-highlight');
// Remove a class with `removeClass()`
$btn.removeClass('js-highlight');
// Toggle a class on/off with `toggleClass()`
$btn.toggleClass('js-highlight');
// Check to see if the element has a class
$btn.hasClass('js-highlight');
```

**Links**

- [jQuery: addClass](http://api.jquery.com/addClass/)
- [jQuery: removeClass](http://api.jquery.com/removeClass/)
- [jQuery: toggleClass](http://api.jquery.com/toggleClass/)
- [jQuery: hasClass](http://api.jquery.com/hasClass/)

---

## Manipulating HTML

When manipulating HTML the [**☛ parent-child relationship**](/topics/html-semantics#parent-child-relationship) is extremely important to remember.

There are a bunch of different functions to manipulate HTML using jQuery.

- `.append()` — will add HTML inside, after all the other children
- `.prepend()` — will add HTML inside, before all the other children
- `.before()` — will add HTML outside, before the element
- `.after()` — will add HTML outside, after the element
- `.remove()` — will completely delete the element
- `.html()` — will replace all the HTML inside the element

Here are some examples:

```html
<ul class="dinos">
  <li class="first">Stegosaurus</li>
</ul>
```

```js
var $dinos = $('.dinos');
var $first = $('.first');

// Add after all the current list items
$dinos.append('<li>Tyrannosaurus</li>');
// Add before all the current list items
$dinos.prepend('<li>Iguanodon</li>');

// Add a new element before the selected element
$first.before('<li>Pteranodon</li>');
// Add a new element after the selected element
$first.after('<li>Dimetrodon</li>');

// Completely delete a list item
$first.remove();

// Replace all the list items with new ones
$dinos.html('<li>Humans</li><li>Birds</li>');
```

*All of the above stuff can be done with plain Javascript but in a more round-about way.*

---

## Form data

Working with forms is very common when it comes to Javascript applications.

### Form submission event

The first thing to do when dealing with forms is to capture the form’s submission event and prevent it from doing what it normally does.

```html
<form class="form" method="post" action="capture-data.html">

</form>
```

```js
var $form = $('.form');

$form.on('submit', function (e) {
  // Stop the form from doing what it normally does
  e.preventDefault();
});
```

### Getting form values

When working with forms we need to get the information from the form and do something with it.

#### Simple values

For simple inputs like: text, number, color, date, time, url, email, etc. we can just use jQuery’s `val()` function.

```js
var $email = $('.email');

// Will get the information the user typed into the input field
$email.val();
```

#### Checkboxes

For checkboxes we need to confirm whether or not the item is checked, like this:

```js
var $terms = $('.terms');

$terms.is(':checked'); // true or false
```

#### Radio buttons

For radio buttons we need to grab them by their group `name` then find the one that has been checked, getting it’s value.

```html
<input type="radio" id="meat" name="diet" value="Meat" checked>
<input type="radio" id="plant" name="diet" value="Plant">
```

```js
$('[name="diet"]:checked').val(); // Meat
```

*It’s important that radio buttons include the `value` attribute when working with them.*

#### Select elements

Select elements work like basic text inputs, but must be set up differently, specifically all the `option` elements need `value` attributes.

```html
<select class="dinos">
  <option value="stego">Stegosaurus</option>
  <option value="trex" selected>Tyrannosaurus</option>
  <option value="pterano">Pteranodon</option>
</select>
```

```js
$('.dinos').val(); // trex
```

---

## Video list

1. [Javascript DOM: selecting HTML elements](https://www.youtube.com/watch?v=q7nSkqmNpMY&index=1&list=PLWjCJDeWfDdexVfek9nZEdmbyBL6_yP6Y)
2. [Javascript DOM: events](https://www.youtube.com/watch?v=YMrUgX2G1dc&index=2&list=PLWjCJDeWfDdexVfek9nZEdmbyBL6_yP6Y)
3. [Javascript DOM: stopping default events](https://www.youtube.com/watch?v=SjwoFeklLPo&index=3&list=PLWjCJDeWfDdexVfek9nZEdmbyBL6_yP6Y)
4. [Javascript DOM: manipulating classes](https://www.youtube.com/watch?v=lU-JdTK6wAE&index=4&list=PLWjCJDeWfDdexVfek9nZEdmbyBL6_yP6Y)
5. [Javascript DOM: manipulating HTML](https://www.youtube.com/watch?v=0m5ytkr25ug&index=5&list=PLWjCJDeWfDdexVfek9nZEdmbyBL6_yP6Y)
6. [Javascript DOM: form data & events](https://www.youtube.com/watch?v=akNM35dRVGQ&index=6&list=PLWjCJDeWfDdexVfek9nZEdmbyBL6_yP6Y)
7. [Javascript DOM: event delegation](https://www.youtube.com/watch?v=JStineSts7s&index=7&list=PLWjCJDeWfDdexVfek9nZEdmbyBL6_yP6Y)

## Supplemental links

- [jQuery Learning Center](http://learn.jquery.com/)
