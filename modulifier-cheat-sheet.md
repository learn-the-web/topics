---
layout: cheatsheet
title: "Modulifier cheat sheet"
tags: "modules object oriented css reuse boilerplate utilities list group buttons icons media object embed containers bem smacss oocss cheat sheet"
desc: "A cheat sheet covering all the classes and utilities provided by Modulifier."

groups:
  - title: "Responsive setup"
    items:
      - name: "*CSS viewport* & *text size*"
        details:
          - "Will includes all the `@viewport` code."
          - "Will set `text-size-adjust` to prevent browsers from zooming text."
      - name: "*Border box*"
        details:
          - "Will add all the `border-box` code to change the layout math."
      - name: "*Body margin*"
        details:
          - "Will remove the default `margin` from `<body>` because it is almost never used."
      - name: "*New HTML elements*"
        details:
          - "Will set default styles for new HTML elements for better browser support."

  - title: "Images"
    items:
      - name: "*Remove border*"
        details:
          - "Will remove the border from all images by default for better browser support."
      - name: "`.img-flex`"
        details:
          - "Creates the responsive `.img-flex` class that will make images `100%` the width of their container."
      - name: "*SVG helpers*"
        details:
          - "Will fix a browser bug related to embedded SVG."
          - "Add the ability for embedded SVG to inherit `fill` from the CSS `color` property."
      - name: "`.image-replacement`, `.ir`"
        details:
          - "A class, and a shorter version, that will hide all the text inside an element and allow only the `background-image` to show."

  - title: "List group"
    note: "These classes are brute force and not responsive, if you use list-group-inline, the list will always be inline."
    items:
      - name: "`.list-group`"
        details:
          - "The `.list-group` class that will remove bullets and padding from lists, so semantically they can be lists but no visually."
          - "When added to a `<dl>` tag, there is a little responsiveness to how the `<dt>` and `<dd>` tags flow."
      - name: "`.list-group-inline`"
        details:
          - "The `.list-group-inline` class that will force the `<li>` tags onto the same line."
          - "When added to the `<dl>` tag, the `<dt>` and `<dd>` tags will sit on the same line if there is enough space."
      - name: "*List group example*"
        details:
          - |
            ```html
            <ul class="list-group-inline">
              <li><a href="#">Dinosaurs</a></li>
              <li><a href="#">Plant eaters</a></li>
              <li><a href="#">Meat eaters</a></li>
            </ul>
            ```

            ```html
            <dl class="list-group-inline">
              <dt>Length</dt>
              <dd>12 metres</dd>
              <dt>Mass</dt>
              <dd>5.4 metric tons</dd>
            </dl>
            ```

  - title: "Embed containers"
    items:
      - name: "`.embed`"
        details:
          - "The wrapper class for making responsive embedded resources like images and videos."
      - name: "`.embed-item`"
        details:
          - "The class to be added directly to the embedded image or video."
      - name: "*Embed container example*"
        details:
          - |
            ```html
            <figure>
              <div class="embed embed-4by3">
                <img class="embed-item" src="dinos.jpg" alt="">
              </div>
              <figcaption>Dinosaurs frolicking in the barren landscape</figcaption>
            </figure>
            ```

            ```html
            <div class="embed embed-16by9">
              <video class="embed-item" src="dinos-frolicking.mp4" controls></video>
            </div>
            ```
      - name: "`.embed-1by1`"
        details:
          - "Square."
      - name: "`.embed-4by3`"
        details:
          - "Traditional TV/computer screens."
      - name: "`.embed-iso216`"
        details:
          - "A-standard paper sizes."
      - name: "`.embed-3by2`"
        details:
          - "Classic 35 mm film & most digital photos, landscape."
      - name: "`.embed-2by3`"
        details:
          - "Classic 35 mm film & most digital photos, portrait."
      - name: "`.embed-golden`"
        details:
          - "The Golden Ratio."
      - name: "`.embed-16by9`"
        details:
          - "HDTV."
      - name: "`.embed-185by100`"
        details:
          - "Common widescreen cinema."
      - name: "`.embed-24by10`"
        details:
          - "Widescreen cinema: 2.4:1."
      - name: "`.embed-3by1`"
        details:
          - "Panorama photos."
      - name: "`.embed-4by1`"
        details:
          - "Polyvision."
      - name: "`.embed-5by1`"
        details:
          - "Really, really wide…"
      - name: "*Making a new ratio*"
        details:
          - "Take the height, divide by the width, and multiply by 100 — `h ÷ w × 100`"
          - "An image with the dimensions: 950 × 1427: `1427 ÷ 950 × 100 = 105%`"

  - title: "Media objects"
    items:
      - name: "`.media`"
        details:
          - "A wrapper class to surround image & text groups, especially if the images is to be beside the text."
      - name: "`.media-img`"
        details:
          - "A class for adding to the image, or surrounding `<div>`, within the media object."
      - name: "`.media-body`"
        details:
          - "A class to add to the text, or surrounding `<div>`, within the media object."
      - name: "`.media-img-reversed`"
        details:
          - "Instead of floating the image left it will `float: right`"
      - name: "`.media-img-stacked`"
        details:
          - "Will disable floating and have the image above the text instead."
      - name: "*Media object example*"
        details:
          - |
            ```html
            <div class="media">
              <div class="media-img media-img-reversed">
                <img src="images/parsnips.jpg" alt="">
              </div>
              <div class="media-body">
                <h2 class="media-title">Parsnips</h2>
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
              </div>
            </div>
            ```

  - title: "Icons"
    items:
      - name: "`.icon`"
        details:
          - "To be added to a tag, usually `<i>` to mark it as being an icon."
          - "Usually you add another class to define the `background-image`"
          - "Will also add some CSS to support embedded SVG icons with the `<svg>` and `<use>` tags."
      - name: "`.icon-label`"
        details:
          - "Can be added to the neighbouring text to allow the icon and the text to align."
      - name: "`.icon-link`"
        details:
          - "Can be added to the surrounding `<a>` tag to remove the `text-decoration`"
      - name: "`.i-16`"
        details:
          - "A 16 × 16 pixel sized icon."
      - name: "`.i-18`"
        details:
          - "A 18 × 18 pixel sized icon."
      - name: "`.i-20`"
        details:
          - "A 20 × 20 pixel sized icon."
      - name: "`.i-24`"
        details:
          - "A 24 × 24 pixel sized icon."
      - name: "`.i-32`"
        details:
          - "A 32 × 32 pixel sized icon."
      - name: "`.i-48`"
        details:
          - "A 48 × 48 pixel sized icon."
      - name: "`.i-64`"
        details:
          - "A 64 × 64 pixel sized icon."
      - name: "`.i-96`"
        details:
          - "A 96 × 96 pixel sized icon."
      - name: "`.i-128`"
        details:
          - "A 128 × 128 pixel sized icon."
      - name: "`.i-192`"
        details:
          - "A 192 × 192 pixel sized icon."
      - name: "`.i-256`"
        details:
          - "A 256 × 256 pixel sized icon."
      - name: "*Icons with `<img>` tags*"
        details:
          - |
            ```html
            <ul>
              <li>
                <i class="icon i-18">
                  <img src="images/icon.svg" alt="">
                </i>
                <span class="icon-label">GitHub</span>
              </li>
            </ul>
            ```
      - name: "*Icons with background images*"
        details:
          - |
            ```html
            <a class="icon-link" href="#">
              <i class="icon i-32 i-github"></i>
              <span class="icon-label">GitHub</span>
            </a>
            ```

            ```css
            .i-github {
              background-image: url("../img/github.svg");
            }
            ```
      - name: "*Icons with SVG symbols*"
        details:
          - |
            ```html
            <svg hidden>
              <symbol id="the-icon" viewBox="0 0 256 256">
                <circle x="128" y="128" r="128" />
              </symbol>
            </svg>

            ⋮

            <a class="icon-link" href="#">
              <i class="icon i-24">
                <svg><use xlink:href="#the-icon"></use></svg>
              </i>
              <span class="icon-label">GitHub</span>
            </a>
            ```

      - name: "*Icons with SVG symbols in a separate file*"
        details:
          - |
            ```html
            <a class="icon-link" href="#">
              <i class="icon i-24">
                <svg><use xlink:href="images/icons.svg#the-icon"></use></svg>
              </i>
              <span class="icon-label">GitHub</span>
            </a>
            ```

  - title: "Hidden"
    items:
      - name: "`[hidden]`, `.hidden`"
        details:
          - "Makes sure the `hidden` attribute works in all browsers and provides a `.hidden` class."
      - name: "`.visually-hidden`"
        details:
          - "A class that will hide something from the visual screen but still allow it to be accessible via tools."
      - name: "`.focusable`"
        details:
          - "To be added to the `.visually-hidden` class to allow the keyboard to access the element."
      - name: "`.invisible`"
        details:
          - "A class that will hide an element on the screen, but its space will still be there."
      - name: "`.chop`, `.crop`"
        details:
          - "These classes that will chop/crop overflowing elements off—essentially just `overflow: hidden`"
      - name: "`.truncate`"
        details:
          - "A class that will chop single lines of text off and add an ellipsis at the end."
      - name: "`.scrollable`"
        details:
          - "A class that make an element horizontally scrollable, good for simple responsive tables."

  - title: "Positioning"
    note: "These classes are brute force and not responsive, if you use left, the element will always be floated left."
    items:
      - name: "`.flex-row`"
        details:
          - "Convert the element into a Flexbox container."
      - name: "`.flex-justify`"
        details:
          - "Turn on Flexbox’s `justify-content: space-between` property."
      - name: "`.flex-align-center`"
        details:
          - "Turn on Flexbox’s `align-items: center` property."
      - name: "`.clearfix`"
        details:
          - "A class that can be used on floating wrappers to trigger a clear fix."
      - name: "`.left`, `.right`"
        details:
          - "Will `float` the element to the `left` or the `right`"
      - name: "`.inline`, `.inline-block` (`.ib`), `.block`"
        details:
          - "Classes to control the `display` property between `inline`, `inline-block`, and `block`"
      - name: "`.valign-top`, `.valign-middle`, `.valign-bottom`"
        details:
          - "These classes allow you to control the `vertical-align` property on `inline` and `inline-block` elements or within tables."
      - name: "`.fixed`, `.relative`, `.absolute`, `.static`"
        details:
          - "Classes to control the `position` property of an element."
      - name: "`.zindex-1`, `.zindex-2`, `.zindex-3`, `.zindex-1000`"
        details:
          - "Classes to control three basic `z-index` states on an element."
      - name: "`.pin-left-top`, `.pin-right-top`, `.pin-left-bottom`, `.pin-right-bottom`, `.pin-center-top`, `.pin-center-bottom`, `.pin-left-center`, `.pin-right-center`, `.pin-center`"
        details:
          - "A series of classes for moving a `position: absolute` element to different common locations."
          - "The `.pin-*` classes will automatically add `position: absolute` so adding the class `.absolute` also isn’t necessary."
          - "Simplified versions are available: `.pin-lt`, `.pin-rt`, `.pin-lb`, `.pin-rb`, `.pin-ct`, `.pin-cb`, `.pin-lc`, `.pin-rc`, `.pin-c`"
      - name: "`.width-quarter`, `.width-half`, `.width-full`"
        details:
          - "A series of classes for setting common widths."
          - "Simplified versions are available: `.w-1-4`, `.w-1-2`, `.w-1`"
      - name: "`.height-quarter`, `.height-half`, `.height-full`"
        details:
          - "A series of classes for setting common heights—usually only useful the context of `position: absolute`"
          - "Simplified versions are available: `.h-1-4`, `.h-1-2`, `.h-1`"
      - name: "`.height-win-quarter`, `.height-win-half`, `.height-win-full`"
        details:
          - "A series of classes for setting elements to have a minimum height compared to the window size."
          - "`.height-win-full` will be the same height as the window itself."
          - "Simplified versions are available: `.h-w-1-4`, `.h-w-1-2`, `.h-w-1`"
      - name: "`.center-flow`, `.center-text`"
        details:
          - "Centres `inline`, `inline-block` & text elements—essentially just adds `text-align: center`"
      - name: "`.center-block`"
        details:
          - "Centres block-level elements, but they need widths—essentially adds: `margin-left: auto; margin-right: auto`"
      - name: "`.center-content`, `.center-content-vertical`"
        details:
          - "Centres all the contents of a box within, both vertically & horizontally centered."
          - "If there are multiple elements they are put on new lines, creating a single column."
      - name: "`.center-content-horizontal`"
        details:
          - "Centres all the contents of a box within, both vertically & horizontally centered."
          - "If there are multiple elements they are put on a single line, creating a row column."
      - name: "`.not-centered`, `.no-auto-margins`"
        details:
          - "Removes the auto margins from the left & right side by setting them to `0`"

  - title: "Nice lists"
    items:
      - name: "*Typographic bullets & numbers*"
        details:
          - "The “Nice lists” option will change the default bullets and numbers on `<ul>` and `<ol>` tags to make them look better."
      - name: "*Remove custom bullets & numbers*"
        details:
          - "The simplest way to remove the custom bullets & numbers is to add the class `.list-group`"

  - title: "Basic buttons"
    items:
      - name: "`.btn`"
        details:
          - "A very basic button style for prototyping websites."
      - name: "`.btn-light`"
        details:
          - "An alternative button style for prototyping websites."
      - name: "`.btn-ghost`"
        details:
          - "A third button style for prototyping websites."
      - name: "`.link-box`"
        details:
          - "For adding to `<a>` tags to remove their underlines and make them block."
      - name: "*Button examples*"
        details:
          - |
            ```html
            <a class="btn" href="#">Buy Now</a>
            <a class="btn btn-ghost" href="#">See all the features</a>
            ```

  - title: "Forms"
    items:
      - name: "*Form normalization*"
        details:
          - "Will normalize a bunch of browser inconsistencies when styling forms and inputs."
          - "Will set all labels to the most accessible visual design format: above inputs—except checkboxes and radio buttons, they will stay beside."
      - name: "`.label-block`"
        details:
          - "A class to force a `<label>` onto its own line."
      - name: "`.label-inline`"
        details:
          - "A class to force a `<label>` onto the same line as other inputs."
      - name: "*Customized input controls*"
        details:
          - "Radio buttons & checkboxes are customized with larger, consistent looking controls."
          - "Select boxes are customized with a consistent look."
      - name: "`.hide-custom-input`"
        details:
          - "This class can be added to a checkbox or radio button `<input>` or `<label>` to hide the custom control."

  - title: "Accessibility"
    items:
      - name: "*Focus styles*"
        details:
          - "Will add strong visual focus styles to links, buttons, inputs and focusable items."
      - name: "*Skip links*"
        details:
          - "Adds all the CSS necessary for creating basic skip links."
      - name: "*Skip links example*"
        details:
          - |
            ```html
            <ul class="skip-links">
              <li><a href="#main">Jump to main content</a></li>
              <li><a href="#nav">Jump to main navigation</a></li>
              <li><a href="#pause">Pause all animations</a></li>
            </ul>
            ```

  - title: "Print styles"
    items:
      - name: "*Print style normalization*"
        details:
          - "Will do a bunch of default things to print styles including: removing shadows, setting text colour to black, removing backgrounds, adding underlines, displaying URLs beside links, and attempting to avoid orphans where possible."
      - name: "`.no-print`"
        details:
          - "Will hide the element when a user prints out the website."
      - name: "`.no-print-href`"
        details:
          - "Will stop the `href` printing out beside a link when printed."
      - name: "`.print-only`"
        details:
          - "Will hide an element by default but then display it when the website is printed."
      - name: "`.force-print`"
        details:
          - "Will attempt to force something to be printed even if there’s JavaScript or some other CSS that tries to hide it."
      - name: "`.page-break-before`"
        details:
          - "Will force a page-break before this content when printed."
      - name: "`.page-break-after`"
        details:
          - "Will force a page-break after this content when printed."
      - name: "`.no-page-break-inside`"
        details:
          - "Will attempt to prevent the content from being broken over multiple pages when printed."
---
