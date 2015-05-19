---
layout: checklist
group: web-dev-1

groups:
  - title: 'Boilerplate'
    items:
      - 'The `<html> tag has a correct `lang` attribute.'
      - 'Includes `<meta charset="utf-8">` immediately after `<head>`.'
      - 'Includes `<title>`.'
      - 'The `<title>` is unique for every page—and isn’t “Untitled”̦.'
      - 'The `<title>` comes after `<meta charset="utf-8">`.'
      - 'CSS files are inside the `<head>`, after the `<title>`.'
      - 'Contains the meta viewport tag.'
      - 'No HTML is outside the `<body>` element.'
      - 'JS files are directly above the closing `</body>`.'

  - title: 'Document'
    items:
      - 'Has a `<header>` tag around the website’s masthead.'
      - 'Has a `<nav>` tag around the most important navigation.'
      - 'Has a `<main>` element around the primary content.'
      - 'Has a `<footer>` tag around the copyright notice.'
      - 'Contains `<article>` and `<section>` tags where appropriate.'

  - title: 'Content'
    items:
      - 'No content is outside of an HTML element.'
      - 'All links go somewhere.<br>[W3C link checker](http://validator.w3.org/checklink)'
      - 'There’s nothing immediately inside `<ul>` & `<ol>` except `<li>` elements.'
      - 'No `<li>` tags are outside of `<ul>` or `<ol>` tags.'
      - 'The `<figure>` isn’t used without a `<figcaption>`.'
      - 'The `<figcaption>` isn’t outside a `<figure>`.'
      - 'There’s nothing immediately inside `<dl>` except `<dt>` & `<dd>` elements.'
      - 'No `<dt>` or `<dd>` tags are outside of a `<dl>`.'
      - 'There’s an appropriate `<h1>` tag on every page.'
      - 'Headings are ordered properly.'

  - title: Data
    items:
      - 'All dates & times are marked up with the `<time>` tag.'
      - 'All data points are marked up with the `<data>` tag.'
      - 'All ranges of numbers are marked up with the `<meter>` tag.'

  - title: 'No-nos'
    items:
      - 'The `<em>` and `<i>` tags are *not* used to make text italic.'
      - 'The `<strong>` and `<b>` tags are *not* used to make text bold.'
      - 'The `<br>` tag is *not* used to make space.'
      - 'The `<hr>` tag is *not* used to make horizontal lines.'

  - title: 'Validation'
    items:
      - 'Every HTML files has been validated.<br>[W3C HTML Validator](http://validator.w3.org/)'
---
