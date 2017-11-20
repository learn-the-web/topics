---
title: "HTML semantics cheat sheet"
tags: "html semantics elements tags cheat sheet"
desc: "A cheat sheet covering the basic HTML elements and their purpose."
layout: cheatsheet

groups:
  - title: 'Document'
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
          - 'When inside `<body>` it’s the website footer.'
          - 'When inside `<article>` it’s the least important information.'
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
      - name: '*CSS link tag*'
        details:
          - |
            ```html
            <link href="css/main.css" rel="stylesheet">
            ```
      - name: '*Navigation inside header*'
        details:
          - |
            ```html
            <header>
              <nav>
                <ul>
                  <li><a href="#">Stegosaurus</a></li>
                  <li><a href="#">Triceratops</a></li>
                  <li><a href="#">Ankylosaurus</a></li>
                </ul>
              </nav>
            </header>
            ```
      - name: '*Main content groups*'
        details:
          - |
            ```html
            <body>
              <header>
                <nav>…</nav>
              </header>

              <main>
                <h1>Dinos-R-Us</h1>
              </main>

              <footer>
                <p>© 2063 Dinos-R-Us</p>
              </footer>
            </body>
            ```

  - title: 'Lists'
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
      - name: '*Unordered list*'
        details:
          - |
            ```html
            <ul>
              <li>Tyrannosaurus</li>
              <li>Spinosaurus</li>
              <li>Velociraptor</li>
            </ul>
            ```
      - name: '*Ordered list*'
        details:
          - |
            ```html
            <ol>
              <li>Mercury</li>
              <li>Venus</li>
              <li>Earth</li>
              <li>Mars</li>
            </ol>
            ```
      - name: '*Description list*'
        details:
          - |
            ```html
            <dl>
              <dt>Length</dt>
              <dd>2.3 m</dd>
              <dt>Weight</dt>
              <dd>4 tonnes</dd>
            </dl>
            ```

  - title: 'Text'
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
      - name: ''
      - name: '*Blockquotes*'
        details:
          - |
            ```html
            <blockquote>
              <p>Dinosaurs may be extinct from the face of the planet, but they are alive and well in our imaginations.</p>
              <footer>— <cite>Steve Miller</cite></footer>
            </blockquote>
            ```
      - name: '*Addresses*'
        details:
          - |
            ```html
            <address>
              Jet Propulsion Laboratory
              <br>4800 Oak Grove Drive
              <br>Pasadena, California
              <br>91109
            </address>
            ```
      - name: '*Text edits*'
        details:
          - |
            ```html
            <p>Launchpad 39A owned by <del datetime="2014-04-14">NASA</del> <ins datetime="2014-04-14">SpaceX</ins></p>
            ```

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
      - name: ''
      - name: '*Basic images*'
        details:
          - |
            ```html
            <img src="images/dino.jpg" alt="An beautiful, long-necked Brontosaurus">
            ```
      - name: '*Figures & captions*'
        details:
          - 'Use only if there’s a caption.'
          - |
            ```html
            <figure>
              <img src="images/dino-small.jpg" alt="">
              <figcaption>So many dinosaurs I can’t even count!</figcaption>
            </figure>
            ```
      - name: '*Responsive images*'
        details:
          - 'See [Responsive & retina images for details](/topics/responsive-retina-images/).'
          - |
            ```html
            <picture>
              <source media="(min-width: 60em)" srcset="images/dino-wide.jpg">
              <source media="(min-width: 38em)" srcset="images/dino-rectangle.jpg">
              <img src="images/dino-small.jpg" alt="All the dinosaurs!">
            </picture>
            ```

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
      - name: ''
      - name: '*Time*'
        details:
          - |
            ```html
            Apollo 11 landed on the moon <time datetime="1969-07-20T20:18">July 20, 1969</time>
            ```
      - name: '*Data*'
        details:
          - |
            ```html
            Argentinosaurus weighted approximately <data value="90">90 tonnes</data>
            ```
      - name: '*Maths*'
        details:
          - |
            ```html
            E = mc<sup>2</sup>
            ```

  - title: 'Meaningless tags'
    items:
      - name: '`<div>`'
        details:
          - 'Inherits meaning from its children.'
          - 'Divides content into logical groups, when no other tag is better suited.'
          - 'Has restrictions on what elements it can be inside.'
      - name: '`<span>`'
        details:
          - 'Inherits meaning from its children.'

  - title: 'Be careful'
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
          - 'Should be used in forms and with JavaScript.'
          - '*Do not use to link to another page—use the `<a>` tag.*'
      - name: '`<wbr>`'
        details:
          - 'Presents an opportunity for the browser to add a line-break if necessary.'
          - 'Groups strings of text, when no other tag is better suited.'

  - title: 'Links'
    items:
      - name: '*Links that go nowhere*'
        details:
          - 'The `href` always needs a value—`#` means nowhere.'
          - |
            ```html
            <a href="#">Nowhere</a>
            ```
      - name: '*Links on the same page*'
        details:
          - 'Add an `id=""` to the element to jump to, refer to that inside the `href`'
          - |
            ```html
            <a href="#herbivores">See the herbivores</a>

            <h2 id="herbivores">Herbivores</h2>
            ```
      - name: '*Links to other files*'
        details:
          - 'Just write the name of the HTML file, also include any folders its inside.'
          - |
            ```html
            <a href="dinos.html">Dinosaurs</a>

            <!-- or in another folder -->
            <a href="herbivores/stegosaurus.html">Stegosaurus</a>
            ```
      - name: '*Links to other websites*'
        details:
          - 'Always start with `https://` or less ideally `http://`'
          - |
            ```html
            <a href="https://www.wikipedia.org/">Wikipedia</a>

            <!-- Adding `rel="external"` for outward-bound sites is good -->
            <a href="https://www.wikipedia.org/" rel="external">Wikipedia</a>
            ```
      - name: '*Links to phone numbers*'
        details:
          - 'Start with `tel:`, use international format'
          - |
            ```html
            <a href="tel:+18005552368">Call Me!</a>
            ```
          - 'Also send a text message with `sms:`'
          - |
            ```html
            <a href="sms:+18005552368&body=Who%20ya%20gonna%20call">Call Me!</a>

            <!-- or without a default number -->
            <a href="sms:&body=Who%20ya%20gonna%20call">Call Me!</a>
            ```
      - name: '*Links to email addresses*'
        details:
          - 'Pops open a new email message, start with `mailto:`'
          - |
            ```html
            <a href="mailto:hey@thomasjbradley.ca">Thomas</a>

            <!-- Add a subject too -->
            <a href="mailto:hey@thomasjbradley.ca?subject=How%20are%20you?">Thomas</a>

            <!-- Even a default body -->
            <a href="mailto:hey@thomasjbradley.ca?subject=How%20are%20you?&body=Hey%20Thomas">Thomas</a>
            ```
          - '`%20` is used to escape spaces—[See more percent-encoding examples](https://en.wikipedia.org/wiki/Percent-encoding)'

  - title: 'Date/time formats'
    notes: 'Apply to the `datetime=""` attribute of the `<time>`, `<del>` & `<ins>` elements.'
    items:
      - name: '*Year*'
        details:
          - 'Format: `YYYY`'
          - 'Example: `1963`'
      - name: '*Year, month*'
        details:
          - 'Format: `YYYY-MM`'
          - 'Example: `1963-11`'
          - '*Nov. 1963*'
      - name: '*Year, month, day*'
        details:
          - 'Format: `YYYY-MM-DD`'
          - 'Example: `1963-11-23`'
          - '*Nov. 23, 1963*'
      - name: '*Year, week*'
        details:
          - 'Format: `YYYY-Wdd`'
          - 'Example: `1963-W47`'
          - '*1936, the week of Nov. 18–24*'
      - name: '*Hour, minute*'
        details:
          - 'Format: `HH:MM`'
          - 'Example: `17:16`'
          - '*5:16 PM*'
      - name: '*Hour, minute, second*'
        details:
          - 'Format: `HH:MM:SS`'
          - 'Example: `17:16:20`'
          - '*5:16:20 PM*'
      - name: '*Hour, minute, second, millisecond*'
        details:
          - 'Format: `HH:MM:SS.sss`'
          - 'Example: `17:16:20.258`'
          - '*5:16:20.258 PM*'
      - name: '*UTC timezone*'
        details:
          - 'Format: `Z`'
          - 'Example: `Z`'
          - '*UTC timezone*'
      - name: '*Timezone offsets*'
        details:
          - 'Format: `±HH:MM`'
          - 'Example: `-05:00`'
          - '*Eastern Standard Time, Daylight Savings*'
      - name: '*Year, month, day, hour, minute*'
        details:
          - 'Format: `YYYY-MM-DDTHH:MM`'
          - 'Example: `1963-11-23T17:16`'
          - '*Nov. 23, 1963 at 5:16 PM*'
      - name: '*Year, month, day, hour, minute, second*'
        details:
          - 'Format: `YYYY-MM-DDTHH:MM:SS`'
          - 'Example: `1963-11-23T17:16:20`'
          - '*Nov. 23, 1963 at 5:16:20 PM*'
      - name: '*Year, month, day, hour, minute, second, millisecond*'
        details:
          - 'Format: `YYYY-MM-DDTHH:MM:SS.sss`'
          - 'Example: `1963-11-23T17:16:20.258`'
          - '*Nov. 23, 1963 at 5:16:20.258 PM*'
      - name: '*Year, month, day, hour, minute, UTC*'
        details:
          - 'Format: `YYYY-MM-DDTHH:MMZ`'
          - 'Example: `1963-11-23T17:16Z`'
          - '*Nov. 23, 1963 at 5:16 PM UTC*'
      - name: '*Year, month, day, hour, minute, timezone*'
        details:
          - 'Format: `YYYY-MM-DDTHH:MM±HH:MM`'
          - 'Example: `1963-11-23T12:16-05:00`'
          - '*Nov. 23, 1963 at 12:16 AM EST*'
      - name: '*Year, month, day, hour, minute, second, timezone*'
        details:
          - 'Format: `YYYY-MM-DDTHH:MM:SS±HH:MM`'
          - 'Example: `1963-11-23T12:16:20-05:00`'
          - '*Nov. 23, 1963 at 12:16:20 AM EST*'
      - name: '*Year, month, day, hour, minute, second, millisecond, timezone*'
        details:
          - 'Format: `YYYY-MM-DDTHH:MM:SS.sss±HH:MM`'
          - 'Example: `1963-11-23T12:16:20.258-05:00`'
          - '*Nov. 23, 1963 at 12:16:20.258 AM EST*'
      - name: '*Period of days*'
        details:
          - 'Format: `PddD`'
          - 'Example: `P686D`'
          - '*686 days*'
      - name: '*Period of days, hours*'
        details:
          - 'Format: `PddDhhH`'
          - 'Example: `P686D23H`'
          - '*686 days, 23 hours*'
      - name: '*Period of days, hours, minutes*'
        details:
          - 'Format: `PddDhhHmmM`'
          - 'Example: `P686D23H18M`'
          - '*686 days, 23 hours, 18 minutes*'
      - name: '*Period of days, hours, minutes, seconds*'
        details:
          - 'Format: `PddDhhHmmMssS`'
          - 'Example: `P686D23H18M14S`'
          - '*686 days, 23 hours, 18 minutes, 14 seconds*'
      - name: '*Period of days, hours, minutes, seconds, milliseconds*'
        details:
          - 'Format: `PddDhhHmmMss.sssS`'
          - 'Example: `P686D23H18M14.400S`'
          - '*686 days, 23 hours, 18 minutes, 14 seconds, 400 milliseconds*'
      - name: '*Exact date example*'
        details:
          - |
            ```html
            <time datetime="1963-11-23T12:16:20Z">Premiere of the most important TV show of all time!</time>
            ```
      - name: '*Simple time period*'
        details:
          - |
            ```html
            <time datetime="P365D6H8M">Earth’s orbital period</time>
            ```
      - name: '*Range of time periods*'
        details:
          - |
            ```html
            Opossum gestation period: <time datetime="P12D">twelve</time> to <time datetime="P13D">thirteen</time> days.
            ```

---
