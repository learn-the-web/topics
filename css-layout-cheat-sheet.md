---
layout: cheatsheet
title: "CSS layout cheat sheet"
tags: "layout position float columns box model flexbox center absolute relative vertical horizontal margin padding cheat sheet"
desc: "A cheat sheet for the basics of CSS layout properties."

groups:
  - title: 'Layout mechanics'
    items:
      - name: '*Display*'
        details:
          - '*Controls how an element is represented within the flow.*'
          - '---'
          - '&nbsp;'
          - '`display: inline`'
          - '![](display-inline.svg)'
          - 'Allows other elements beside; margin, padding & width don’t work.'
          - '---'
          - '&nbsp;'
          - '`display: block`'
          - '![](display-block.svg)'
          - 'Takes up an entire line; margin, padding & width work.'
          - '---'
          - '&nbsp;'
          - '`display: inline-block`'
          - '![](display-inline-block.svg)'
          - 'Allows other elements beside; margin, padding & width work. Can create columns, but will force a space between boxes.'
      - name: '*Float*'
        details:
          - '*Controls whether text is wrapped around the element.*'
          - '---'
          - '&nbsp;'
          - '`float: left|right|none`'
          - '![](float.svg)'
          - 'Allows other elements to wrap around the element.'
          - '---'
          - '&nbsp;'
          - 'Multiple floats'
          - '![](multi-float.svg)'
          - 'Can create columns with boxes touching sides.'
          - '---'
          - '&nbsp;'
          - '`clear: left|right|both`'
          - '![](clear.svg)'
          - 'Force the element below floated elements.'
          - '---'
          - '&nbsp;'
          - '`overflow: hidden`'
          - '![](overflow.svg)'
          - 'Use on a parent element to force it to wrap around the floated children—a clearfix.'
      - name: '*Position*'
        details:
          - '*Gives strict, coordinate-based control over layout.*'
          - '---'
          - '&nbsp;'
          - '`position: absolute`'
          - '![](absolute.svg)'
          - 'Move an element around based on coordinates.'
          - '---'
          - '&nbsp;'
          - '`position: relative`'
          - '![](relative.svg)'
          - 'Added to a parent element to reset absolute child’s coordinates.'
          - '---'
          - '&nbsp;'
          - '`position: fixed`'
          - '![](fixed.svg)'
          - 'Forces an element to not move when the page is scrolled.'
          - '---'
          - '&nbsp;'
          - '`z-index`'
          - '![](z-index.svg)'
          - 'Control the stacking order of elements—higher number is closer.'

  - title: 'Centering elements'
    items:
      - name: '`text-align: center`'
        details:
          - 'Works only on `display: inline` & `inline-block` elements.'
          - '*Must be applied to the parent element.*'
          - |
            ```html
            <figure class="img-box">
              <img src="images/argentinosaurus.jpg" alt="">
              <figcaption>The mighty Argentinosaurus</figcaption>
            </figure>
            ```
          - |
            ```css
            .img-box {
              text-align: center;
            }
            ```
      - name: '`margin: 0 auto`'
        details:
          - 'Works only on `display: block` elements.'
          - '*The element must have a `width`*'
          - |
            ```html
            <div class="box">Stegosaurus</div>
            ```
          - |
            ```css
            .box {
              width: 24em; /* Without a width `auto` won’t work */
              margin-left: auto;
              margin-right: auto;
            }
            ```
          - 'You can also specify just `margin-left: auto` and `margin-right: auto` if you want margins on the top or bottom.'
      - name: '`vertical-align: middle`'
        details:
          - 'Works only on `display: inline` & `inline-block` elements.'
          - '*Must be applied to the parent element.*'
          - |
            ```html
            <ul>
              <li>Pteranodon</li>
              <li>Quetzalcoatlus</li>
            </ul>
            ```
          - |
            ```css
            ul {
              vertical-align: middle;
            }

            ul li {
              display: inline-block;
            }
            ```
      - name: '*Centering absolute*'
        details:
          - 'Use `transform` & `50%` coordinates to center an absolutely positioned element.'
          - |
            ```html
            <div class="banner">
              <div class="content">
                <h1>Micropachycephalosaurus</h1>
                <p>Longest dinosaur name ever!</p>
              </div>
            </div>
            ```
          - |
            ```css
            .banner {
              position: relative;
            }

            .content {
              position: absolute;
              left: 50%;
              transform: translateX(-50%);
            }
            ```
          - '*Or vertical centering too…*'
          - |
            ```css
            .content {
              position: absolute;
              left: 50%;
              top: 50%;
              transform: translate(-50%, -50%);
            }
            ```
      - name: '*Centering with float*'
        details:
          - '*There’s no `float: center`*'
          - '**You cannot center floated elements.**'
      - name: '*Centering with flexbox*'
        details:
          - 'Flex box has a bunch of different alignment classes—*that are always applied to the parent*.'
          - |
            ```html
            <div class="card">
              <h2>Edmontosaurus</h2>
              <a href="#">See the bones!</a>
            </div>
            ```
          - |
            ```css
            .card {
              display: flex;
              flex-direction: column;
              justify-content: center;
              align-content: center;
              align-items: center;
            }
            ```
          - '*This will be completely centered within the box.*'
          - '[See the flexbox cheat sheet for more details.](/topics/flexbox-cheat-sheet/)'

  - title: 'Common code'
    items:
      - name: '*Border box*'
        details:
          - 'Used to change layout math for width & padding.'
          - '**Put at the top of every CSS file.**'
          - |
            ```css
            html {
              box-sizing: border-box;
            }

            *, *::before, *::after {
              box-sizing: inherit;
            }
            ```
      - name: '*Clearfix for float*'
        details:
          - 'Add to the parent elements of floats to force the parent to surround the floated element.'
          - 'Can be used instead of `overflow: hidden`'
          - |
            ```css
            .clearfix::after {
              content: " ";
              display: block;
              clear: both;
            }
            ```
      - name: '*Flexible images*'
        details:
          - 'Use `width` & `display` to make images flex to their parent’s size.'
          - |
            ```css
            img {
              display: block;
              width: 100%;
            }
            ```
---
