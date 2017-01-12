---
title: "CSS selectors & units cheat sheet"
tags: "css selectors class id units rem px percent cheat sheet"
desc: "A cheat sheet covering the basics of CSS selectors and units."
layout: cheatsheet

groups:
  - title: 'Selectors'
    items:
      - name: '`Tag`'
        details:
          - 'Select all the tags of the same type.'
          - |
            ```css
            html {}
            h1 {}
            p {}
            ```
      - name: '`.` — Class'
        details:
          - 'Select an element that has a class.'
          - |
            ```css
            .masthead {}
            .nav {}
            .contact {}
            ```
      - name: '`#` — ID'
        details:
          - 'Select an element that has the ID.'
          - |
            ```css
            #heading-1 {}
            #github {}
            #top {}
            ```
      - name: '`Space` — Descendant'
        details:
          - 'Select an element that’s a descendant of another element.'
          - |
            ```css
            ul li {}
            nav a {}
            ul li {}
            ```
      - name: '`>` — Child'
        details:
          - 'Select an element directly inside another element.'
          - |
            ```css
            ul > li {}
            h1 > span {}
            footer > .copyright {}
            ```
      - name: '`+` — Adjacent sibling'
        details:
          - 'Select an element immediately beside another element.'
          - |
            ```css
            h1 + p {}
            hr + p {}
            li + li {}
            ```
      - name: '`~` — General sibling'
        details:
          - 'Select an element that’s at the same level.'
          - |
            ```css
            p ~ p {}
            h1 ~ p {}
            dd ~ dt {}
            ```
      - name: '`[]` — Attribute'
        details:
          - 'Select an element by it’s attribute.'
          - 'Good for styling links differently if they’re external.'
          - |
            ```css
            [data-state="active"] {}
            [href^="http" {}
            [download] {}
            ```
          - '[More on attribute selectors below.](#attribute-selectors)'

  - title: 'Pseudo classes'
    items:
      - name: '`:first-child`'
        details:
          - 'Select the element when it’s the first inside its parent.'
          - |
            ```css
            p:first-child {}
            ul li:first-child {}
            .person:first-child {}
            ```
      - name: '`:last-child`'
        details:
          - 'Select the element when it’s the last inside its parent.'
          - |
            ```css
            li:last-child {}
            p:last-child {}
            .item:last-child {}
            ```
      - name: '`:only-child`'
        details:
          - 'Select an element when it’s the only thing inside its parent.'
          - |
            ```css
            li:only-child {}
            ```
      - name: '`:nth-child()`'
        details:
          - 'Select an element by it’s number.'
          - 'Good for zebra-striping table rows.'
          - |
            ```css
            li:nth-child(2) {}
            tr:nth-child(odd) {}
            div:nth-child(5n) {}
            ```
      - name: '`:nth-last-child()`'
        details:
          - 'Select an element by it’s number, counting backwards from the end.'
          - |
            ```css
            /* Third from the bottom */
            li:nth-last-child(3) {}
            ```
      - name: '`:nth-of-type()`'
        details:
          - 'Select an element by it’s number, but only counting others that match—not all children.'
          - |
            ```css
            /* Second <p> element in its parent */
            p:nth-of-type(2) {}
            ```
      - name: '`:nth-last-of-type()`'
        details:
          - 'Select an element by it’s number, counting backwards from the end.'
          - |
            ```css
            /* Second <p> from the bottom */
            p:nth-last-of-type(2) {}
            ```
      - name: '`:first-of-type`'
        details:
          - 'Select an element that’s the first of its kind within its parent.'
          - |
            ```css
            p:first-of-type {}
            ```
      - name: '`:last-of-type`'
        details:
          - 'Select an element that’s the last of its kind within its parent.'
          - |
            ```css
            p:last-of-type {}
            ```
      - name: '`:only-of-type`'
        details:
          - 'Select an element when it’s the only child of its parent of a specific kind.'
          - |
            ```css
            p:only-of-type {}
            section div:only-of-type {}
            ```
      - name: '`:empty`'
        details:
          - 'Select an element it has no children.'
          - |
            ```css
            ul:empty {}
            ```
      - name: '`:disabled`'
        details:
          - 'Select an element when its `disabled` attribute is set.'
          - |
            ```css
            button:disabled {}
            ```
      - name: '`:checked`'
        details:
          - 'Select an `<input>` when its `checked` attribute is set.'
          - |
            ```css
            input:checked {}
            ```
      - name: '`:target`'
        details:
          - 'Select an element when the URL matches its ID.'
          - |
            ```css
            li:target {}
            ```
      - name: '`:not()`'
        details:
          - 'Select matching elements that *do not* match the selection inside the `()`'
          - |
            ```css
            p:not(.mammal) {}
            input:not(:checked) {}
            ```

  - title: 'Pseudo elements'
    items:
      - name: '`::before`'
        details:
          - 'A hidden element before the content of most elements.'
          - |
            ```css
            blockquote::before {
              content: "“";
              font-size: 5rem;
            }
            ```
          - '[Learn more about ::before.](/topics/before-after/)'
      - name: '`::after`'
        details:
          - 'A hidden element after the content of most elements.'
          - |
            ```css
            blockquote::after {
              content: "”";
              font-size: 5rem;
            }
            ```
          - '[Learn more about ::after.](/topics/before-after/)'
      - name: '`::first-line`'
        details:
          - 'Select the first line of text.'
          - 'Good for highlighting the first line of a paragraph.'
          - |
            ```css
            p::first-line {}
            ```
      - name: '`::first-letter`'
        details:
          - 'Select the first character in the text.'
          - 'Good for drop caps.'
          - |
            ```css
            p::first-letter {}
            ```
      - name: '`::selection`'
        details:
          - 'Style an element when it has been selected and highlighted.'
          - |
            ```css
            ::selection {
              color: red;
            }
            ```

  - title: 'Interaction selectors'
    items:
      - name: '`:link`'
        details:
          - 'For styling a link that hasn’t been visited.'
          - |
            ```css
            a:link {
              color: #4484c2;
            }
            ```
      - name: '`:visited`'
        details:
          - 'For styling a link that has been visited.'
          - |
            ```css
            a:visited {
              color: #ccc;
            }
            ```
      - name: '`:hover`'
        details:
          - 'For styling an element when the mouse hovers over it.'
          - |
            ```css
            a:hover {
              color: #00f;
            }
            ```
      - name: '`:focus`'
        details:
          - 'For styling an element for when the keyboard focuses it.'
          - 'Only works on `<a>`, `<button>`, and form inputs by default.'
          - |
            ```css
            button:focus {
              outline: 3px solid #000;
              outline-offset: 2px;
            }
            ```
      - name: '`:active`'
        details:
          - 'For styling an element when the mouse button is clicked down on it.'
          - |
            ```css
            a:active {
              color: #f33;
            }
            ```

  - title: 'Attribute selectors'
    items:
      - name: '*Has an attribute*'
        details:
          - 'Select when an element has a specific attribute.'
          - |
            ```css
            [download] {}
            ```
      - name: '*Exact match*'
        details:
          - 'Select when an attribute that’s exactly the same.'
          - |
            ```css
            [rel="external"] {}
            [data-state="visible"] {}
            ```
      - name: '*Starts with*'
        details:
          - 'Select when an attribute starts with some text.'
          - |
            ```css
            [href^="http://"] {}
            ```
      - name: '*Ends with*'
        details:
          - 'Select when an attribute ends with some text.'
          - |
            ```css
            [src$=".jpg"] {}
            ```
      - name: '*Contains*'
        details:
          - 'Select when an attribute contains some text anywhere.'
          - |
            ```css
            [class*="unit"] {}
            ```
      - name: '*Contains when separated by spaces*'
        details:
          - 'Select an element when its attribute matches one item from a space separated list.'
          - |
            ```html
            <p class="unit xs-1 s-1 m-1"></p>
            ```
            ```css
            [class~="s-1"] {}
            ```
      - name: '*Contains when separated by dashes*'
        details:
          - 'Select an element when its attribute matches one item from a dash separated list.'
          - |
            ```html
            <p class="super-duper-long-class-name"></p>
            ```
            ```css
            [class|="duper"] {}
            ```
      - name: '*Case insensitive*'
        details:
          - 'Allows the search to ignore upper vs. lower case letters.'
          - |
            ```css
            [lang="en-ca" i] {}
            ```

  - title: 'Colours'
    items:
      - name: '**Keywords**'
        details:
          - 'Standardized, named colours. [Color keywords](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#Color_keywords).'
          - |
            ```css
            background-color: red;
            color: darkorange;
            border-color: hotpink;
            ```
      - name: '**Hexadecimal**'
        details:
          - 'Hex colours start with a hash: `#`.'
          - 'Three separate numbers: red, green, blue.'
          - |
            ```css
            background-color: #000000;
            color: #ff3333;
            border-color: #b95f4;
            outline-color: darkorange;
            ```
          - 'Simplify pairs: `#000`, `#fff`, `#f33`'
          - |
            ```css
            background-color: #000;
            border-color: #fff;
            color: #f22;
            ```
      - name: '**RGB**'
        details:
          - 'Specify colours using red, green & blue numbers.'
          - |
            ```css
            background-color: rgb(255, 255, 255);
            color: rgb(255, 0, 0);
            border-color: rgb(124, 65, 99);
            ```
      - name: '**RGBA**'
        details:
          - 'RGB with semi-transparent/opacity.'
          - |
            ```css
            background-color: rgba(0, 0, 0, .5);
            color: rgba(255, 0, 0, .75);
            border-color: rgba(124, 65, 99, .8);
            ```
      - name: '**HSL**'
        details:
          - 'Specify colours using the hue, saturation, lightness system.'
          - 'Different from Photoshop’s HSB system.'
          - |
            ```css
            background-color: hsl(0, 100%, 100%);
            color: hsl(53, 100%, 50%);
            border-color: hsl(167, 38%, 59%);
            ```
          - '[HSL Color Picker](http://hslpicker.com/)'
      - name: '**HSLA**'
        details:
          - 'HSL with semi-transparent/opacity.'
          - |
            ```css
            background-color: hsla(0, 100%, 100%, .5);
            color: hsla(53, 100%, 50%, .7);
            border-color: hsla(167, 38%, 59%, .3);
            ```
      - name: '**Transparency**'
        details:
          - 'The `transparent` keyword can be used to remove a colour.'
          - |
            ```css
            background-color: transparent;
            ```
      - name: '**Current colour**'
        details:
          - 'The `currentColor` keyword can be used to capture the `color` of the same element.'
          - |
            ```css
            color: red;
            border-color: currentColor; /* Will be red */
            ```

  - title: 'Units'
    items:
      - name: '`px`'
        details:
          - '*CSS pixels*—different sizes for every device.'
          - '`100px` is exactly 100 pixels in all situations.'
      - name: '`em`'
        details:
          - 'Based on the font-size of the parent (or current element).'
          - '`1em` is 1 × the parent element’s size.'
          - '`0.5em` is 0.5 × the parent element’s size.'
      - name: '`rem`'
        details:
          - 'Based on the font-size set in the `html` element.'
          - '`1.5rem` is 1.5 × the `html` element’s font size.'
      - name: '`%`'
        details:
          - '*Percentage*'
          - 'A percentage of the parent element.'
          - '`100%` is to whole width of the parent element.'
          - 'If the parent element is `50%` wide, and this element is `50%` wide, then it only takes up `25%` of the original grand parent element.'
      - name: '`vh`'
        details:
          - '*Viewport height*'
          - 'Like percentage, but based on the height of the window.'
          - '`100vh` is the whole height of the window.'
          - '`50vh` is half the height of the window.'
      - name: '`vw`'
        details:
          - '*Viewport width*'
          - 'Like percentage, but based on the width of the window.'
          - '`75vw` is three-quarters the width of the window.'

  - title: 'Unit rules'
    items:
      - name: '**Use `rem` for `font-size`**'
        details:
          - 'Always use `rem` for font sizes because it’s easier to manage.'
          - '**Never—ever—user `px` for font sizes.**'
      - name: '**Use `rem` or `em` for paddings and margins**'
        details:
          - 'The idea being that we want the margins and paddings to increase when the font size increases.'
          - 'Most often I use `em` for `padding` and `rem` for `margin`'
      - name: '**Use `%` for widths**'
        details:
          - 'Most often use `%` for widths because we want most things to be flexible.'
          - 'Sometimes using `px` or `em` for widths is okay too.'
      - name: '**Use `em` for maximum widths**'
        details:
          - 'Maximum widths required a fixed measurement—so `em` for `max-width` works because we want the `max-width` to increase as the font size increases.'
      - name: '**Use `px` for borders and accuracy**'
        details:
          - 'Use pixels for accuracy—when things should *always* be the same size: logos as an example.'
          - 'Or use pixels for borders—though sometimes `em` for `border` is cool too.'
          - '**Never—ever—user `px` for font sizes.**'
---
