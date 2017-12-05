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
          - 'Create space outside the box, pushing other boxes.'
          - |
            ```css
            /* See above for examples of the value system */
            margin: 1.125em;
            margin: 1.125em 1em;
            ```
          - 'Target each side individually: `margin-top`, `margin-right`, `margin-bottom`, `margin-left`'
          - |
            ```css
            margin-top: .875em;
            margin-bottom: 0;
            ```
      - name: '*negative margins*'
        details:
          - 'Because margins are outside of a box they can actually have negative numbers.'
          - 'Instead of pushing other boxes away, negative margins pull the box in a specific direction.'
          - |
            ```css
            margin-left: -5rem;
            ```
          - 'Will pull the box to the left by `5em` and can cause elements to overlap.'
      - name: '`padding`'
        details:
          - 'Create space inside the box, pushing text away from the edge.'
          - |
            ```css
            /* See above for examples of the value system */
            padding: 1em;
            margin: 1em .8em;
            ```
          - 'Target each side individually: `padding-top`, `padding-right`, `padding-bottom`, `padding-left`'
          - |
            ```css
            padding-left: 1em;
            padding-right: .875em;
            ```
      - name: '`width`'
        details:
          - 'Control the horizontal space of a box.'
          - |
            ```css
            width: 100px;
            width: 50%; /* of the element its inside */
            width: 100vw; /* Full width of the window */
            ```
      - name: '`height`'
        details:
          - 'Controls the vertical space of a box.'
          - '**Setting a height should be avoided at all costs.**'
          - 'Let the content inside the box dictate the height.'
          - |
            ```css
            height: 25px; /* BAD! */
            ```
      - name: '`min-width`'
        details:
          - 'Make a box be at least a certain width, but can expand.'
          - |
            ```css
            min-width: 100px;
            ```
      - name: '`min-height`'
        details:
          - 'Make a box at least a certain height, but can expand.'
          - '*This is infinitely better than just `height`*'
          - |
            ```css
            min-height: 12em;
            min-height: 75vh; /* 75% height of the window */
            ```
      - name: '`overflow`'
        details:
          - 'Control how elements that break out the edges of the box are dealt with.'
          - 'One of: `visible`, `hidden`, `scroll`, `auto`'
          - |
            ```css
            overflow: hidden; /* Chop off everything */
            overflow: auto; /* Introduce a scrollbar if necessary */
            ```
          - 'Also contorl a single direction: `overflow-x`, `overflow-y`'
          - |
            ```css
            overflow-x: hidden;
            overflow-y: scroll;
            ```
      - name: '`calc()`'
        details:
          - 'Sometimes we can’t calculate a value ahead of time because it depends on something the browser knows but we don’t, e.g. adding `em` + `px` together.'
          - |
            ```css
            width: calc(100vw - 10px);
            padding-left: calc(1.4em + 24px);
            ```
          - '**Always have a space around the math operator!**'
          - |
            ```css
            width: calc(100vw-10px); /* Not gonna work */
            ```

  - title: 'Colours & borders'
    items:
      - name: '`color`'
        details:
          - 'Set the colour of the text.'
          - |
            ```css
            color: red;
            color: #fff;
            ```
      - name: '`background-color`'
        details:
          - 'Set the colour of the box, behind the text.'
          - |
            ```css
            background-color: orange;
            background-color: #e2e2e2;

            /* Semi-transparent colour */
            background-color: rgba(0, 0, 0, .5);
            ```
      - name: '`border-width`'
        details:
          - 'Control the thickness of the stroke around a box.'
          - |
            ```css
            border-width: 12px;

            /* Or use em if you want it to scale with the text size */
            border-width: .1em;
            ```
      - name: '`border-color`'
        details:
          - 'Set the colour of the box stroke.'
          - |
            ```css
            border-color: indigo;
            border-color: #f33;
            ```
      - name: '`border-style`'
        details:
          - 'Set the visual appearance of the line.'
          - 'Possible values: `solid`, `dashed`, `dotted`, `double`, `groove`, `ridge`, `inset`, `outset`'
          - |
            ```css
            border-style: solid;
            border-style: dotted;
            ```
      - name: '`border` shorthand'
        details:
          - 'A short form version for setting the three border properties.'
          - '`border:`'
          - '• `border-width`'
          - '• `border-style`'
          - '• `border-color`'
          - |
            ```css
            border: 3px solid black;
            border: 4px dotted green;
            ```
      - name: '*Borders on single sides*'
        details:
          - 'Target each side of the box using `border-*` properties.'
          - '`border-top`, `border-right`, `border-bottom`, `border-left`'
          - |
            ```css
            border-top: 3px solid indigo;
            border-bottom: 3px solid indigo;
            ```
          - 'There’s also all the other singular properties like `border-top-width`, `border-bottom-style` but I rarely use those.'
      - name: '`border-radius`'
        details:
          - 'Make the corners of the box slightly rounded.'
          - |
            ```css
            border-radius: 4px;
            border-radius: .3em;
            ```
          - 'Control each side differently, start on top-left, go clockwise around.'
          - |
            ```css
            border-radius: 4px 6px 10px 12px;
            ```
          - 'Do ovals using a `/` to separate the different axes'
          - |
            ```css
            border-radius: 4px/10px;
            ```
          - '[Border-radius generator.](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Background_and_Borders/Border-radius_generator)'
      - name: '`opacity`'
        details:
          - 'Make the whole box and all its content semi-transparent.'
          - 'A number between `0` & `1`'
          - |
            ```css
            opacity: .5;
            opacity: .2;
            ```
      - name: '`box-shadow`'
        details:
          - 'Create a drop-shadow behind the box.'
          - 'Requires at least 3 values:'
          - '`box-shadow:`'
          - '• `horizontal-offset`'
          - '• `vertical-offset`'
          - '• optionally: `blur-radius`'
          - '• optionally: `spread-radius`'
          - '• `color`'
          - |
            ```css
            box-shadow: 2px 2px black;
            box-shadow: 2px 2px 10px rgba(0, 0, 0, .5);
            box-shadow: 2px 2px 10px 4px rgba(0, 0, 0, .5);

            /* Move the shadow inside the box with inset */
            box-shadow: inset 2px 2px black;
            ```
          - '[Box-shadow generator.](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Background_and_Borders/Box-shadow_generator)'
      - name: '*Multiple box-shadows*'
        details:
          - 'Separate each box-shadow with a comma.'
          - |
            ```css
            box-shadow: 2px 0 red, -2px 0 green;
            ```
      - name: '`outline`'
        details:
          - 'Like a border, but outside border, doesn’t take up space, will overlap surrounding elements.'
          - |
            ```css
            outline: 3px solid black;
            ```
          - '`outline-offset` — will push the outline away from the box edge.'
          - |
            ```css
            outline-offset: 2px;
            ```

  - title: 'Box sizing systems'
    items:
      - name: '`box-sizing: content-box`'
        details:
          - '**Do not use `content-box`**'
          - 'The default box calculation math puts the padding & border outside the width set in CSS.'
          - 'This causes all sorts of confusing math solutions on responsive sites and just makes our coding life annoying.'
          - '*Example calculation:*'
          - |
            ```css
            /*
              Total width of box is 130px:
              100px + 10px (left) + 10px (right) + 5px (left) + 5px (right) = 130px
            */
            .box {
              width: 100px;
              padding: 10px;
              border-width: 5px;
            }
            ```
      - name: '`box-sizing: border-box`'
        details:
          - '**Always use `border-box`**'
          - 'Simplifies the responsive math by making the width of a box, as set in CSS, not change by adding padding and border.'
          - '**Always include this snipped of CSS!**'
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
          - '*Example calculation:*'
          - |
            ```css
            /*
              Total width of box is: 100px, defined by width
            */
            .box {
              width: 100px;
              padding: 10px;
              border-width: 5px;
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
