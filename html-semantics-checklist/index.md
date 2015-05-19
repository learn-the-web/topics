---
layout: checklist
group: web-dev-1

groups:
  - title: 'Boilerplate'
    items:
      - 'The `<html>` tag has a correct `lang` attribute.'
      - 'Includes `<meta charset="utf-8">` immediately after `<head>`.'
      - 'Includes `<title>`.'
      - 'The `<title>` is unique for every page—and isn’t “Untitled”̦.'
      - 'The `<title>` comes after `<meta charset>`.'
      - 'CSS files are inside the `<head>`, after the `<title>`.'
      - 'Contains the meta viewport tag.'
      - 'No HTML is outside the `<body>` element.'
      - 'JS files are directly above the closing `</body>`.'

  - title: 'Document'
    items:
      - 'A `<header>` tag is around the website’s masthead.'
      - 'A `<nav>` tag is around the most important navigation.'
      - 'A `<main>` element is around the primary content.'
      - 'A `<footer>` tag is around the copyright notice.'
      - 'Contains `<article>` and `<section>` tags where appropriate.'

  - title: 'Content'
    items:
      - 'All content has a semantically appropriate element & no content is outside of an element.'
      - 'There’s an appropriate `<h1>` tag on every page.'
      - 'Headings are ordered properly.'
      - 'All links go somewhere.<br>[W3C link checker](http://validator.w3.org/checklink)'
      - 'The `<figure>` isn’t used without a `<figcaption>`.'

  - title: Data
    items:
      - 'All dates & times are marked up with `<time>`.'
      - 'All data points are marked up with `<data>`.'
      - 'All ranges of numbers are marked up with `<meter>`.'

  - title: 'No-nos'
    items:
      - 'The `<em>` and `<i>` tags are *not* used to make text italic.'
      - 'The `<strong>` and `<b>` tags are *not* used to make text bold.'
      - 'The `<br>` tag is *not* used to make space.'
      - 'The `<hr>` tag is *not* used to make horizontal lines.'

  - title: 'Validation'
    items:
      - 'The document is perfectly indented.<br>[HTML indentation](/topics/html-indentation/)'
      - 'Every HTML file has been validated.<br>[W3C HTML Validator](http://validator.w3.org/)'
      - 'There’s nothing immediately inside `<ul>` & `<ol>` except `<li>` elements.'
      - 'No `<li>` tags are outside of `<ul>` or `<ol>`.'
      - 'The `<figcaption>` isn’t outside a `<figure>`.'
      - 'There’s nothing immediately inside `<dl>` except `<dt>` & `<dd>` elements.'
      - 'No `<dt>` or `<dd>` tags are outside of a `<dl>`.'
---
