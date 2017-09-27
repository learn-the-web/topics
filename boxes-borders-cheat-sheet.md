---
layout: cheatsheet
title: "Boxes & borders cheat sheet"
tags: "css box model border outline width height color shadow opacity sizing margin padding cheat sheet"
desc: "A cheat sheet covering the CSS box model and associated properties."

groups:
  - title: 'The Box Model'
    items:
      - name: '*The CSS Box Model*'
        width: 'double'
        details:
          - '![An illustration of the box-model properties](box-model.svg)'
          - 'Starting at the content and working out:'
          - '• `padding` — space between the content & box edge; `background-color` fills behind this space.'
          - '• `border` — line around the edge of the box.'
          - '• `margin` — space outside the box, pushing other boxes away; can see through margin to what’s behind.'
      - name: '*Margin & padding number order*'
        details:
          - '![An illustration of the margin/padding value system](margin-padding-order.svg)'
          - '`margin` & `padding` can take 1–4 values.'
          - 'With 4 values, we start at the top and continue clockwise around the box.'
          - |
            ```css
            /* 10px on all four sizes of the box */
            margin: 10px;
            /* 10px top/bottom; 12px left/right */
            margin: 10px 12px;
            /* 10px top; 12px left/right; 14px bottom */
            margin: 10px 12px 14px;
            /* 10px top; 12px right; 14px bottom; 16px left */
            margin: 10px 12px 14px 16px;
            ```
          - '*The same system applies completely to `padding`*'
  - title: 'Box dimensions'
    items:
      - name: '`margin`'
        details:
          - '`margin-top`, `margin-right`, `margin-bottom`, `margin-left`'
      - name: '`padding`'
        details:
          - '`padding-top`, `padding-right`, `padding-bottom`, `padding-left`'
      - name: '`width`'
      - name: '`height`'
      - name: '`min-width`'
      - name: '`min-height`'
      - name: '`overflow`'
        details:
          - '`overflow-x`, `overflow-y`'
      - name: '`calc()`'

  - title: 'Colours & borders'
    items:
      - name: '`color`'
      - name: '`background-color`'
      - name: '`border-width`'
      - name: '`border-color`'
      - name: '`border-style`'
      - name: '`border`'
      - name: '*Borders on single sides*'
      - name: '`border-radius`'
        details:
          - 'Different border radius for different sides'
      - name: '`opacity`'
      - name: '`box-shadow`'
      - name: '`outline`'
      - name: '`outline-offset`'

  - title: 'Box sizing systems'
    items:
      - name: '`box-sizing: content-box`'
        details:
          - '**Do not use `content-box`**'
      - name: '`box-sizing: border-box`'
        details:
          - '**Always use `border-box`**'
          - |
            ```css
            /* This snipped of CSS should always be included */
            html {
              box-sizing: border-box;
            }

            *, *::before, *::after {
              box-sizing: inherit;
            }
            ```
      - name: '*Border box vs. content box*'
        details:
          - '![An illustration of border-box vs. content-box](box-sizing.svg)'

  - title: 'Display & layout'
    notes: 'See the [CSS layout cheat sheet](/topics/css-layout-cheat-sheet/) for more detail.'
    items:
      - name: '`display: inline`'
        details:
          - 'Flows content together, fitting on the same line if possible.'
          - '`margin`, `padding`, `width` **don’t work**.'
      - name: '`display: block`'
        details:
          - 'Takes up a whole line by itself.'
          - '`margin`, `padding`, `width` **do work.**'
      - name: '`display: inline-block`'
        details:
          - 'A hybrid between `block` & `inline`: fits on the same line, allows `padding`, `width`, etc.'
      - name: '`display: none`'
        details:
          - 'Completely hide the element from the page.'
          - 'Set to another `display` value to make it visible again.'
---
