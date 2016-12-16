---
layout: cheatsheet

groups:
  - title: Document
    items:
      - name: '`<title>`'
        details:
          - 'Second most important piece of content.'
          - 'Shown in the browser tab & search results.'
          - 'Should be unique for *every* page on the site.'
      - name: '`<link href="…" rel="stylesheet">`'
        details:
          - 'For linking CSS and other resources like feeds.'
          - '`href` is the path the file.'
          - '`rel` has different values for other resources.'
      - name: '`<header>`'
        details:
          - 'When inside `<body>` it’s the website masthead.'
          - 'When inside `<article>` it’s the most important information.'
      - name: '`<footer>`'
        details:
          - 'When inside `<body> it’s the website footer.'
          - 'When inside `<article> it’s the least important information.'
      - name: '`<main>`'
        details:
          - 'Primary content of the page.'
      - name: '`<nav>`'
        details:
          - 'Defines a group a navigation links.'
      - name: '`<article>`'
        details:
          - 'A piece of content that’s independent.'
          - 'Could be removed from this website and still make sense.'
      - name: '`<section>`'
        details:
          - 'A group in a series of related content pieces.'
      - name: '`<aside>`'
        details:
          - 'Secondary content not required to understand the main content.'

  - title: Lists
    items:
      - name: '`<ul>`'
        details:
          - 'An unordered list—the order of items isn’t important.'
          - 'Can only have `<li>` elements as direct children.'
      - name: '`<ol>`'
        details:
          - 'An ordered list—the order of the items is important.'
          - 'Could be alphabetical, numerical, best to worst, etc.'
          - 'Can only have `<li>` elements as direct children.'
      - name: '`<li>`'
        details:
          - 'A single list item.'
          - 'Must be inside a `<ul>` or `<ol>`.'
          - 'Can have most other elements inside it.'
      - name: '`<dl>`'
        details:
          - 'A description list—a grouping of terms and definitions.'
          - 'Words & definitions, titles & summaries, data points, etc.'
          - 'Can only have `<dt>` and `<dd>` elements as direct children.'
      - name: '`<dt>`'
        details:
          - 'Description title, the term of the item.'
          - 'Must come before the `<dd>`.'
      - name: '`<dd>`'
        details:
          - 'Description definition, the data, or text of the item.'
          - 'Can be multiple `<dd>` tags underneath one `<dt>`.'

  - title: Text
    items:
      - name: '`<a href="…">`'
        details:
          - 'For making hyperlinks.'
          - '`href` is the path to where the link should go.'
      - name: '`<h1>`'
        details:
          - 'The *most* important piece of content on the page.'
          - 'On the homepage this should be the company’s name.'
          - 'On inside pages this should be the page title.'
      - name: '`<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>`'
        details:
          - 'Content headings, each a sub-heading of the one above.'
          - 'The `<h2>` is a sub-heading of `<h1>`, `<h3>` a sub-heading of `<h2>`, etc.'
      - name: '`<p>`'
        details:
          - 'A generic paragraph of text.'
      - name: '`<blockquote>`'
        details:
          - 'A large, stand alone quote from another source.'
      - name: '`<cite>`'
        details:
          - 'A citation for another source, often used with quotations.'
          - 'A person’s name, a URL, a book, a movie title, etc.'
      - name: '`<q>`'
        details:
          - 'A small quotation embedded within other content.'
      - name: '`<em>`'
        details:
          - 'A string of emphasized, slightly more important text.'
          - 'Screen readers will change their voice for this text.'
      - name: '`<strong>`'
        details:
          - 'A string of highly emphasized, much more important text.'
          - 'Screen readers will change their voice for this text.'
      - name: '`<ins datetime="…">`'
        details:
          - 'Content that was inserted after the document was published.'
          - '`datetime` defines when it was added.'
      - name: '`<del datetime="…">`'
        details:
          - 'Content that was deleted after the document was published.'
          - '`datetime` defines when it was removed.'
      - name: '`<abbr title="…">`'
        details:
          - 'An acronym or abbreviation, like “HTML”, “CSS”, etc.'
          - '`title` contains the expanded version, like “Hypertext Markup Language”.'
      - name: '`<dfn>`'
        details:
          - 'A definition of a term on the page.'
          - 'Should only be used once of the term.'
      - name: '`<mark>`'
        details:
          - 'Used to highlight a piece of text for reference.'
          - 'The keywords in a search results page, the current navigation item.'
      - name: '`<i>`'
        details:
          - 'Defines technical term, a ship name, a book title, a thought, sarcasm, another language.'
      - name: '`<b>`'
        details:
          - 'Defines a keyword, like product name in a review, a lead sentence in a paragraph.'
      - name: '`<s>`'
        details:
          - 'Content that’s no longer relevant to the document.'
          - 'Consider if the `<del>` element is better suited first.'
      - name: '`<u>`'
        details:
          - 'Labels the text as having a non-textual annotation.'
          - 'A misspelled word, a Chinese proper name, etc.'
      - name: '`<small>`'
        details:
          - 'Represents side comments and fine print.'
      - name: '`<address>`'
        details:
          - 'Contact information, email, tel, postal address, etc.'

  - title: 'Images & media'
    items:
      - name: '`<img src="…" alt="…">`'
        details:
          - 'Embeds an image that’s important to the content.'
          - '`src` is a path to the image file.'
          - '`alt` describes the image if it cannot be seen.'
      - name: '`<figure>`'
        details:
          - 'Embeds annotated images, illustrations, photos, code, etc.'
          - 'Could be moved out of place and would still make sense.'
      - name: '`<figcaption>`'
        details:
          - 'For adding a caption/annotation to the `<figure>`.'
          - 'Must be inside a `<figure>` element—cannot stand alone.'
      - name: '`<picture>`'
        details:
          - 'Responsive image insertion—allows developers to provide different images for different contexts.'
      - name: '`<video poster="…" autoplay loop muted controls>`'
        details:
          - 'For embedding movies into a website.'
          - '`poster` is the path to an image that’s displayed before the video plays.'
          - '`autoplay` will hint the video to start automatically.'
          - '`loop` triggers whether the video should repeat or not.'
          - '`muted` can be added to not play sound by default.'
          - '`controls` shows or hides the browser’s player buttons.'
      - name: '`<audio autoplay loop muted controls>`'
        details:
          - 'For embedding sounds into a website.'
          - '`autoplay` will hint the audio to start automatically.'
          - '`loop` triggers whether the audio should repeat or not.'
          - '`muted` can be added to not play sound by default.'
          - '`controls` shows or hides the browser’s player buttons.'
      - name: '`<source>`'
        details:
          - 'Must be inside `<picture>`, `<video>` or `<audio>` to define the different versions of content.'
          - 'For example, in video it gives paths to the MP4 and WEBM formats.'
      - name: '`<track>`'
        details:
          - 'Used to pair captions, chapters, etc. with `<video>` elements.'

  - title: 'Data & code'
    items:
      - name: '`<sub>`'
        details:
          - 'Defines text as being subscript.'
      - name: '`<sup>`'
        details:
          - 'Defines text as being superscript.'
      - name: '`<var>`'
        details:
          - 'Represents a variable in math or programming.'
      - name: '`<time datetime="…">`'
        details:
          - 'Marks some text as a time or date.'
          - '`datetime` defines the machine readable version.'
      - name: '`<data value="…">`'
        details:
          - 'Marks elements as being a numerical piece of information.'
          - '`value` provides the machine readable version.'
      - name: '`<meter value="…" min="…" max="…">`'
        details:
          - 'Represents a single number in a range of numbers.'
          - '`value` is the current number.'
          - '`min` is the minimum number.'
          - '`max` is the maximum number.'
      - name: '`<progress value="…" min="…" max="…">`'
        details:
          - 'Represents the current position in a series of steps.'
          - '`value` is the current position.'
          - '`min` is the minimum position.'
          - '`max` is the maximum position.'
      - name: '`<code>`'
        details:
          - 'Defines a piece of text as a code sample.'
      - name: '`<pre>`'
        details:
          - 'A piece of text that has a specific formatting, where tabs, whitespaces, etc. should be maintained.'
      - name: '`<kbd>`'
        details:
          - 'Something a user should type into their computer.'
      - name: '`<samp>`'
        details:
          - 'Something a user should see output from a computer.'

  - title: Meaningless tags
    items:
      - name: '`<div>`'
        details:
          - 'Inherits meaning from its children.'
          - 'Divides content into logical groups, when no other tag is better suited.'
          - 'Has restrictions on what elements it can be inside.'
      - name: '`<span>`'
        details:
          - 'Inherits meaning from its children.'
          - 'Groups strings of text, when no other tag is better suited.'

  - title: Be careful
    items:
      - name: '`<br>`'
        details:
          - 'Creates a line break that’s significant to the content.'
          - 'Useful in poems and addresses where the division of lines is important.'
          - '*Do not use to create space in a design—use margins and padding.*'
      - name: '`<hr>`'
        details:
          - 'Represents a thematic break in the content.'
          - 'For example, a scene change or topic change.'
          - '*Do not use to create a horizontal line—use CSS borders.*'
      - name: '`<button>`'
        details:
          - 'Represents a interactive, clickable button.'
          - 'Should be used in forms and with Javascript.'
          - '*Do not use to link to another page—use the `<a>` tag.*'
      - name: '`<wbr>`'
        details:
          - 'Presents an opportunity for the browser to add a line-break if necessary.'

---
