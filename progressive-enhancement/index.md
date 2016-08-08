---
playlist: PLWjCJDeWfDdfJs0Bd7oIVrPn6ealKYgZQ
download: https://github.com/acgd-learn-the-web/progressive-enhancement-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/progressive-enhancement-code
---

It’s our job, as web designers and developers, to accommodate as many possible uncertainties and allow our content to be consumed by anybody, anywhere, anytime.

---

## It’s about everybody

Since the web is open and available to every human being, throughout the world, there are a many uncertainties we have to understand and accommodate. The only thing we can be certain about is that the content will be consumed—beyond that we know very little.

### Your user is not you

> The power of The Web is in its universality. Access by everyone regardless of disability is an essential aspect.
> — Tim Berners-Lee, W3C Director and inventor of the World Wide Web

Don’t assume everybody has a large resolution monitor. Don’t assume everybody has a super-fast–always-on internet connection. Don’t assume everybody can *see* your design. Don’t assume everybody can tell the difference between red and green. And don’t assume that your content will be consumed just on your website.

There is very little we know about our users and a lot we don’t know:

- We don’t know where in the world our users are coming from;
- We don’t know what time of day our users will consume our content;
- We don’t know what format or context our content will be consumed in;
- We don’t know what devices our users are using;
- We don’t know our users’ browser window size;
- We don’t know our users’ internet connection speed;
- We don’t know the mindset of our users;
- And we don’t know what abilities our users have.

(From: [CSS-Tricks: What We Don’t Know](http://css-tricks.com/14664-what-we-dont-know/).)

All we know is that our users are human (unless they’re robots.)

Your users are not you. The Open Web opens so many doors for every human being. It’s our job as web designers to empower humans by helping them easily consume our website’s content—independent of their abilities, independent of their computer’s abilities, and often independent of the original source: our website.

**We can control all situations but we need to try to make our website functional for as many people as possible.**

### Checklist of what-ifs

Here’s a big checklist of things to consider when developing your website. These things could happen for many different reasons, often not the user’s choice.

*You’ll notice many of these overlap with performance and accessibility—in fact progressive enhancement is very closely related.*

- ❏ What if the images don’t download or aren’t visible?
- ❏ What if the images are black & white?
- ❏ What if the font-size is significantly larger? Or smaller?
- ❏ What if CSS is disabled or doesn’t load?
- ❏ What if the browser doesn’t support newer CSS features?
- ❏ What if the browser doesn’t support newer HTML features?
- ❏ What if they’re using a text-only browser?
- ❏ What if the browser is smaller? Or bigger?
- ❏ What if they’re using only a keyboard?
- ❏ What if they’re using a touch device?
- ❏ What if Javascript is disabled?
- ❏ What if there’s a Javascript error and it doesn’t run?
- ❏ What if the Internet connection is slow?
- ❏ What if the user prints out the website?
- ❏ What if your user isn’t giving their full attention?
- ❏ What if there is double the amount of content on the page?
- ❏ What if your content is consumed on another website?

**Most of all, test in as many browsers as you can—especially with Javascript off.**

**Links**

- **[Everyone has JavaScript, right?](http://kryogenix.org/code/browser/everyonehasjs.html)**
- [A fictional conversation about progressive enhancement](https://tommorris.org/posts/9370)

---

## Detecting CSS features

Browsers are not a single platform, each browser supports a different set of features. Often one set of features will work great in one browser but not in another browser and we need to have different CSS for different scenarios.

### Modernizr

[Modernizr](http://modernizr.com/) is a popular Javascript solution that detects CSS, HTML & Javascript features. There are two different ways to use it: through CSS classes or through the Javascript interface.

1. On the Modernizr website, configure what features you want to test on the download page.
2. Generate your version of Modernizr.
3. Put the Javascript you get into a file named `modernizr.min.js` and include it on your website.

When it comes to Modernizr, it’s often best to put it in the `<head>` of your HTML file. That’s usually a performance no-no because it pauses rendering in the browser. In the case of Modernizr we don’t want the website rendered until after Modernizr has run.

```html
<head>
  <script src="js/modernizr.min.js"></script>
</head>
```

#### Modernizr CSS classes

After Modernizr runs in the browser it will add classes to the `<html>` element, you’ll end up with something like this:

```html
<!DOCTYPE html>
<html class="csstransforms">
```

So, if the browser supports `transform` we’ll get a class named `csstransforms`, if the browser doesn’t support transforms we’ll get a class named `no-csstransforms`.

In our CSS we can then do something like this:

```css
h1 {
  transform: rotate(45deg);
}

.no-csstransforms h1 {
  /* Do something different for non-supporting browsers */
}
```

#### Modernizr Javascript conditionals

We can also use Modernizr in our Javascript code with the `Modernizr` object.

In our Javascript we could write something like this:

```js
if (!Modernizr.csstransforms) {
  /* Do something when CSS transforms aren’t supported */
}
```

### Detecting without Javascript

There’s a new CSS property that we can use in some browsers—eventually it will be a very powerful solution.

We can use native feature detection using the `@supports` declaration:

```css
@supports (transform-style: preserve-3d) {
  /* Put your parallax code in here */
}
```

**[See the @supports availability on Can I Use.](http://caniuse.com/#feat=css-supports-api)**

**Links**

- **[Modernizr](http://modernizr.com/)**
- [CSS @supports](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports)

---

## Modern browsers only

Sometimes we only want to target our Javascript at fairly modern browsers. We should detect each Javascript feature before we use them to confirm the browser has the abilities we need.

*That doesn’t mean the website becomes unusable without Javascript, just that users can still access all the information but with a different user experience.*

### Cutting the mustard

The [BBC](http://responsivenews.co.uk/post/18948466399/cutting-the-mustard) came up with a technique they call “Cutting the Mustard”: if the browser doesn’t cut the mustard it doesn’t get the Javascript.

In the BBC article they choose to test for three major features: `querySelector`, `localStorage` & `addEventListener`. We can test these in Javascript and keep the results in a variable:

```js
var cutsTheMustard = ('querySelector' in document && 'localStorage' in window && 'addEventListener' in window);
```

Then using an if-statement we can load our Javascript file if the browser passes the test:

```js
var js;

if (cutsTheMustard) {
  js = document.createElement('script');
  js.src = 'js/enhanced.js';
  js.async = true;
  document.querySelector('script').parentNode.appendChild(js);
}
```

*This is a very, very basic Javascript script loader, check out the links for a few more below.*

**Links**

- [BBC: Cutting the Mustard](http://responsivenews.co.uk/post/18948466399/cutting-the-mustard)
- [Cut the mustard revisited](https://justmarkup.com/log/2015/02/26/cut-the-mustard-revisited/)

**Loaders**

- [Babel](https://babeljs.io/)
- [webpack](https://webpack.github.io/)
- [Browserify](http://browserify.org/)
- [Exploring ES6: Modules](http://exploringjs.com/es6/ch_modules.html)
- [ES6 In Depth: Modules](https://hacks.mozilla.org/2015/08/es6-in-depth-modules/)

---

## Javascript on & off

When Javascript is off we don’t need to provide an identical experience for the user—we just need to make sure the content is available.

### Progressively enhanced tabs

For tabs, as an example, the non-Javascript experience would just be a list with internal links that jump down to the appropriate pieces of content. There are no visual tabs but a list of content where each of the tab panels are always visible.

When the Javascript executes, it builds the tab interface back up, triggering the appropriate CSS, adding the ARIA attributes, and making the tabs function as we’re used to.

We don’t need to have the ARIA attributes on the default non-JS version because ARIA is primarily for interactions built with Javascript.

- [See working progressively enhanced tabs.](http://demos.learn-the-web.algonquindesign.ca/progressive-enhancement/tabs.html)
  *Make sure to test with Javascript turned off.*
- [Browse commented progressively enhancement tabs code.](https://github.com/acgd-learn-the-web/progressive-enhancement-code/blob/gh-pages/js/tabs.js)

---

## Video list

1. [Progressive enhancement: detecting CSS features](https://www.youtube.com/watch?v=DHpr10QSEcg&list=PLWjCJDeWfDdfJs0Bd7oIVrPn6ealKYgZQ&index=1)
2. [Progressive enhancement: cutting the mustard](https://www.youtube.com/watch?v=zbMJtxDD-4I&list=PLWjCJDeWfDdfJs0Bd7oIVrPn6ealKYgZQ&index=2)
3. [Progressive enhancement: tabs](https://www.youtube.com/watch?v=22v5nl4lFok&index=3&list=PLWjCJDeWfDdfJs0Bd7oIVrPn6ealKYgZQ)

## Supplemental links

- [This is a motherfucking website.](http://motherfuckingwebsite.com/)
- [This is still a motherfucking website.](http://bettermotherfuckingwebsite.com/)
- [Best mother fucking website.](https://bestmotherfucking.website/)
- [Wikpedia: Progressive enhancement](https://en.wikipedia.org/wiki/Progressive_enhancement)
- [Designing with Progressive Enhancement](https://www.filamentgroup.com/dwpe/) & [Code samples](https://www.filamentgroup.com/dwpe/code/)
- [The True Cost of Progressive Enhancement](http://blog.easy-designs.net/archives/the-true-cost-of-progressive-enhancement/)
- [Pragmatic progressive enhancement - why you should bother with it](http://icant.co.uk/articles/pragmatic-progressive-enhancement/)
- [Gov.uk: Progressive enhancement](https://www.gov.uk/service-manual/making-software/progressive-enhancement.html)
- [Understanding Progressive Enhancement](http://alistapart.com/article/understandingprogressiveenhancement)
- [Progressive Enhancement 101: Overview and Best Practices](http://sixrevisions.com/web-development/progressive-enhancement/)
- [The Real Progressive Enhancement](http://adamsilver.io/articles/the-real-progressive-enhancement/)
- [The design of datalist](https://adactio.com/journal/4272)
- [Progressive Enhancement: Zed’s Dead, Baby](http://tomdale.net/2013/09/progressive-enhancement-is-dead/)
- [Design Consistency for the Responsive Web](https://docs.google.com/presentation/d/10xurAtRO5tCN4UjqbgbBnASXlVYsX-wul9A3w3-FfBc/edit?pli=1)
