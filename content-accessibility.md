---
title: "Content accessibility"
tags: "accessibility humans impairments visual mobility dexterity auditory cognitive color blindness memory deafness transcript captions wai aria landmark roles skip links focus styles tools total validator screen readers VoiceOver braille"
desc: "Making our content work well for every human being regardless of their abilities."
playlist: content-accessibility
cheatsheet: accessibility-cheat-sheet
checklist: accessibility-checklist
download: https://github.com/learn-the-web/accessibility-code/archive/master.zip
github: https://github.com/learn-the-web/accessibility-code
---

So much of the Web is made up of content & text. We need to work to help that content & text be available and accessible to all humans to use our website. With a few key considerations the text can work for everbody.

---

## Language

One of the most important things you can do to your website to enhance accessibility it to use plain, simple language.

Make everything clear, obvious, readable to humans—and completely understandable to the target audience.

Choose the appropriate grammar, words, acronyms. Consider the best sentence length, paragraph length and document length. Consider chunking the content, using headings & lists & text highlights to guide readers.

---

## Semantics

Semantics of your website are a very important aspect of accessibility—probably the most important aspect.

**The HTML tags you choose & how you use them dramatically affects usability & accessibility of the content.**

### How do semantics affect understanding?

Let’s explore a few examples of where semantics have a big change on understanding—especially for people who cannot see your website.

#### Why use heading tags?

Let’s say we write a heading in out HTML like this—which is completely valid HTML:

```html
<strong>Dinosaurs are amazing!</strong>
```

(And visually, with CSS, we made it big & bold and obviously a heading.)

A screen reading tool, like VoiceOver, would only read: **“Dinosaurs are amazing!”** (maybe with a stressed tone because of the `<strong>` tag).

But that doesn’t help orient our users. It doesn’t help them understand the structure. It doesn’t help them navigate the website.

Of course, we should use an appropriate header tag, like this:

```html
<h1>Dinosaurs are amazing!</h1>
```

(Now, visually it doesn’t matter so much what it _looks_ like because it means something specific.)

A screen reader will read something like **“Heading level 1 Dinosaurs are amazing!”**. But not only that our users can get a list of all the headings on the page—in order. And they can jump between headings.

#### Why use lists?

We could write a list in HTML like this—and style it with CSS to look perfectly like a list:

```html
<div>
  <p>Triassic Period</p>
  <p>Jurassic Period</p>
  <p>Cretaceous Period</p>
</div>
```

A screen reader would read something as simple as **“Triassic Period (pause) Jurassic Period (pause) Cretaceous Period”**. This doesn’t help our users understand the content.

Let’s rewrite it with better semantics:

```html
<ol>
  <li>Triassic Period</li>
  <li>Jurassic Period</li>
  <li>Cretaceous Period</li>
</ol>
```

Screen readers present much more information with this HTML, they’ll say something like:

**Ordered list, 3 items
<br>Triassic Period, item 1 of 3
<br>Jurassic Period, item 2 of 3
<br>Cretaceous Period, item 3 of 3
<br>End of list**

This helps users use our website for a few reasons:

- It tells them it’s a list of things—in a specific order
- It tells them how many things are in the list
- It moves through the list in order, reminding of the order
- It tells them when the list has finished
- It provides way to navigate up & down the list
- It provides a way to jump over the list
- It may even provide a way to see all the lists on a page

#### Choose HTML tags wisely

So, semantics provide extra information that help people use our website, help them understand the contenet if they can’t see it & help them navigate.

_Always consider what the information means & what can be communicated to people to help them understand the information._

### Logical order

Keep your code & your content in your HTML documents in the order you expect them to be read. In the logical order of the content.

We want to avoid rearranging the order of content to support a specfic layout. Always prioritize content over layout.

### Headings

Break up your content using heading tags. They’re nice visual breaks, but screen readers use them as jumping points.

You can bring up a list of all the headings on the page and jump to whichever you want.

#### Outlines

Make sure your headings are in the proper numerical order. Don’t skip numbers. It can be especially confusing for people with screen readers because they may think they missed some content on the page.

- Have one—and only one—`<h1>` tag on your page
- Use sub headings as necessary, always being away of the numbered heading above & being sure the headings are realted

### HTML validators

HTML validators are tools that help use confirm we’ve structured our content properly. They don’t determine if we’ve chosen the correct tags and used the correct semantics.

They only confirm that the code is written properly.

But they can be very helpful for accessibility: if you forget to close a tag that could change the semantics of all elements coming after by semantically embedding the elements in the unclosed tag.

The W3C HTML validator will also provide you with a outline of your headings so you can confirm the structure makes sense.

**Links**

- [Living HTML validator](https://validator.nu/)
- [Official W3C HTML validator](https://validator.w3.org/)

---

## Image descriptions

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

### Decorative images

Images should always have an `alt` attribute—unless they’re purely for decoration. If the image doesn’t contribute to the content make the alt attribute empty.

```html
<img src="swirls.jpg" alt="">
```

For even better accessibility, consider adding an ARIA role to the image to completely hide it from a screen reader.

```html
<img src="swirls.jpg" alt="" role="presentation">
```

*If we add `role="presentation"` to our images they will be completely ignored by screen readers.*

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

_Only use the figure element if your image needs a caption, if you don’t need a caption, don’t use the figure._

**Links**

- [MDN: figure](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure)
- [MDN: figcaption](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figcaption)

### Extended descriptions for images

Often there’s complex graphics on your page that need accessible descriptions. The `alt` doesn’t provide a place for complex descriptions, only short overviews.

As an example, say you have an infographic on your website. First, if it can be done in HTML & CSS with real text do that. If it must be a raster image, then use `aria-details` to write HTML describing the content of the image.

```html
<img aria-details="#infographic-desc" src="big-complex-infographic.jpg" alt="">

<div id="infographic-desc">
  <h2>All about dinosaurs</h2>
  <h3>Meat eaters</h3>
  <ul>
    <li>…</li>
    ⋮
</div>
```

The `aria-details` attribute can point to a location on the current page or a location on another page.

It is best to keep that information visible on the screen, but if you must hide it the `hidden` attribute should work okay.

There’s a similar ARIA property: `aria-describedby`—the difference is that `aria-details` allows multiple HTML elements that are navigable where `describedby` will mash all the elements into a single sentence stream.

**[☛ Check out the tutorial on JavaScript for more ARIA examples.](/topics/javascript-jquery-accessibility/)**

**Links**

- **[UX accessibility with aria-label](https://dev.opera.com/articles/ux-accessibility-aria-label/)**
- [Periodic Table of ARIA 1.0 attributes](https://dylanb.github.io/periodic-aria-attributes.html)
- [Periodic Table of ARIA 1.0 Roles](https://dylanb.github.io/periodic-aria-roles.html)
- [WAI-ARIA: An introduction to Accessible Rich Internet Applications](https://patrickhlauke.github.io/aria/presentation/)
- [WAI-ARIA](http://www.w3.org/TR/wai-aria-1.1/)
- [Using WAI-ARIA Landmarks](http://www.paciellogroup.com/blog/2013/02/using-wai-aria-landmarks-2013/)
- [Connect with aria-describedby](http://www.last-child.com/accessible-infographics/infographics-aria-describedby/)
- [On HTML belts and ARIA braces](http://html5doctor.com/on-html-belts-and-aria-braces/)
- [MDN: An overview of accessible web applications and widgets](https://developer.mozilla.org/en-US/docs/Web/Accessibility/An_overview_of_accessible_web_applications_and_widgets)
- [Where to Put Your Search Role](http://adrianroselli.com/2015/08/where-to-put-your-search-role.html)
- [WAI-ARIA Screen Reader Compatibility](http://www.powermapper.com/tests/screen-readers/aria/index.html)

---

## WAI-ARIA roles & properties

The Accessible Rich Internet Application specification defines whole bunch of roles and attributes that can be assigned to HTML elements to help them be understood.

We may make tabs in HTML with lists and divs, and they may look like tabs, but to accessibility tools like screen readers they’re just lists and divs. ARIA allows us to turn them into functional and understandable tabs with a few extra properties & some JavaScript.

### Landmark roles

Adding ARIA landmark roles to your website is a great way to provide navigational landmarks for people using accessibility tools like screen readers. With roles, people using screen readers can jump directly to specific locations on the website.

The major landmark roles for websites are:

- `banner` — for defining an element as the masthead, added to the primary `<header>`.
- `navigation` — for defining an element as the primary navigation, added the the top `<nav>`.
- `search` — for defining an element as being the search field, usually added to a `<div>` surround your search `<form>`.
- `main` — for defining an element as being the main content of the page, same as the `<main>` element, and added to the `<main>`.
- `complementary` — for defining an element as being content related to the primary content, usually added to an `<aside>`.
- `contentinfo` — for defining an element as information about the content: e.g. copyright, terms, privacy policy, usually added to a `<footer>`.

Here’s an example of adding the landmark role to the masthead:

```html
<header role="banner">
  <strong>Accessible Website</strong>
</header>
```

**Every piece of content on a page should be contained within one of these landmark roles.**

### Properties

You can use the ARIA properties to help define extra information about your content so that accessibility tools can more fully understand it.

#### Labeling links

Here’s an example: you have a list of blog posts on your page and they all have a “Read more” link.

```html
<ol>
  <li>
    <h2>Dinosaur discovery</h2>
    <p>New dinosaur discovered</p>
    <a href="…">Read more</a>
  </li>
  <li>
    <h2>Famous dinosaur hunter hunted</h2>
    <p>Being a dinosaur hunter is bad business</p>
    <a href="…">Read more</a>
  </li>
</ol>
```

A screen reader might read something like:

**Ordered list, 2 items
<br>List item 1
<br>Dinosaur discovery, heading level 2
<br>New dinosaur discovered
<br>Link, Read more
<br>List item 2
<br>Famous dinosaur hunter hunted, heading level 2
<br>Being a dinosaur hunter is bad business
<br>Link, Read more**

While going through the list step-by-step, that’s okay, as long as we can use our memory to associate the heading to the link.

But one really important tool in screen readers is listing all the links on the page. The screen reader would list all the links like:

**Read more
<br>Read more**

Since all the links say the same thing they aren’t good for accessibility because, by themselves, they don’t mean anything.

Ideally you could change the link to say something else, by adding the title of the blog post in, like **“Read more about the newly discovered dinosaur”**. This can become a little visually cumbersome on the page, so we can use ARIA to provide that information without it being visual.

Add the `aria-label` attribute to the item to give it a non-visual label that can be used by accessibility tools, like screen readers that will announce the information.

```html
<ul>
  <li>
    <h2>…</h2>
    <p>…</p>
    <a href="…" aria-label="Read more about the newly discovered dinosaur"
      >Read more</a
    >
  </li>
  ⋮
</ul>
```

Screen readers might say:

**Ordered list, 2 items
<br>List item 1
<br>Dinosaur discovery, heading level 2
<br>New dinosaur discovered
<br>Link, Read more about the newly discovered dinosaur
<br>⋮**

<!--

---

## Audio transcripts

@TODO Write a tutorial on audio transcripts

---

## Video captions

@TODO Write a tutorial on video captions

-->

---

## Video list

1. [Content accessibility: ARIA landmark roles](https://videos.learntheweb.courses/playlists/content-accessibility#1-aria-roles)
1. [Content accessibility: Labeling links](https://videos.learntheweb.courses/playlists/content-accessibility#2-aria-label)
1. [Content accessibility: Extended descriptions for images](https://videos.learntheweb.courses/playlists/content-accessibility#3-aria-describedat)
1. [Content accessibility: Validators](https://videos.learntheweb.courses/playlists/content-accessibility#4-validators)
1. [Content accessibility: VoiceOver](https://videos.learntheweb.courses/playlists/content-accessibility#5-voiceover)
