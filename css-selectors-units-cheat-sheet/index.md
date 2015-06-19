---
layout: cheatsheet
group: web-dev-1

groups:
  - title: 'Selectors'
    items:
      - name: '`Tag`'
        details:
          - 'Select all the tags of the same type.'
          - '*Examples:* `html`, `h1`, `p`'
      - name: '`.` — Class'
        details:
          - 'Select an element that has a class.'
          - '*Examples:* `.masthead`, `.nav`, `.contact`'
      - name: '`#` — ID'
        details:
          - 'Select an element that has the ID.'
          - '*Examples:* `#heading-1`, `#facebook`, `#top`'
      - name: '`Space` — Descendant'
        details:
          - 'Select an element that’s a child of another element.'
          - '*Examples:* `ul li`, `nav a`, `footer ul li`'
      - name: '`>` — Direct descendant'
        details:
          - 'Select an element directly inside another element.'
          - '*Examples:* `ul > li`, `h1 > span`, `footer > .copyright`'
      - name: '`+` — Adjacent sibling'
        details:
          - 'Select an element immediately beside another element.'
          - '*Examples:* `h1 + p`, `hr + p`, `li + li`'
      - name: '`~` — General sibling'
        details:
          - 'Select an element that’s at the same level.'
          - '*Examples:* `p ~ p`, `h1 ~ p`, `dd ~ dd`'
      - name: '`[]` — Attribute'
        details:
          - 'Select an element by it’s attribute.'
          - 'Good for styling links differently if they’re external.'
          - '*Examples:* `[data-state="active"]`, `[href^="http"]`, `[download]`'


  - title: 'Pseudo classes'
    items:
      - name: '`:first-child`'
        details:
          - 'Select the element when it’s the first inside its parent.'
          - '*Examples:* `p:first-child`, `ul li:first-child`, `.person:first-child`'
      - name: '`:last-child`'
        details:
          - 'Select the element when it’s the last inside its parent.'
          - '*Examples:* `li:last-child`, `p:last-child`, `.item:last-child`'
      - name: '`:nth-child()`'
        details:
          - 'Select an element by it’s number.'
          - 'Good for zebra-striping table rows.'
          - '*Examples:* `li:nth-child(2)`, `tr:nth-child(odd)`, `div:nth-child(5n)`'
      - name: '`::first-line`'
        details:
          - 'Select the first line of text.'
          - 'Good for highlighting the first line of a paragraph.'
          - '*Examples:* `p::first-line`'
      - name: '`::first-letter`'
        details:
          - 'Select the first character in the text.'
          - 'Good for drop caps.'
          - '*Examples:* `p::first-letter`'
      - name: '`:target`'
        details:
          - 'Select an element when the URL matches its ID.'
          - '*Examples:* `li:target`'
      - name: '`::selection`'
        details:
          - 'Style an element when it has been selected and highlighted.'
          - '*Examples:* `::selection { color: red; }`'

  - title: 'Interaction selectors'
    items:
      - name: '`:link`'
        details:
          - 'For styling a link that hasn’t been visited.'
      - name: '`:visited`'
        details:
          - 'For styling a link that has been visited.'
      - name: '`:hover`'
        details:
          - 'For styling an element when the mouse hovers over it.'
      - name: '`:focus`'
        details:
          - 'For styling an element for when the keyboard focuses it.'
          - 'Only works on `<a>`, `<button>`, and form inputs by default.'
      - name: '`:active`'
        details:
          - 'For styling an element when the mouse button is clicked down on it.'

  - title: 'Colours'
    items:
      - name: '**Keywords**'
        details:
          - 'Standardized, named colours.'
          - '*Examples:* `red`, `white`, `darkorange`, `hotpink`, `limegreen`'
          - '[Color keywords](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#Color_keywords).'
      - name: '**Hexadecimal**'
        details:
          - 'Hex colours start with a hash: `#`.'
          - 'Three separate numbers: red, green, blue.'
          - '*Examples:* `#000000`, `#ffffff`, `#ff3333`, `#b95f48`'
          - 'Simplify pairs: `#000`, `#fff`, `#f33`'
      - name: '**RGB**'
        details:
          - 'Specify colours using red, green & blue numbers.'
          - '*Examples:* `rgb(255, 255, 255)`, `rgb(255, 0, 0)`, `rgb(124, 65, 99)`'
      - name: '**RGBA**'
        details:
          - 'RGB with semi-transparent/opacity.'
          - '*Examples:* `rgba(0, 0, 0, .5)`, `rgba(255, 0, 0, .75)`, `rgba(124, 65, 99, .8)`'
      - name: '**HSL**'
        details:
          - 'Specify colours using the hue, saturation, lightness system.'
          - 'Different from Photoshop’s HSB system.'
          - '*Examples:* `hsl(0, 100%, 100%)`, `hsl(53, 100%, 50%)`, `hsl(167, 38%, 59%)`'
          - '[HSL Color Picker](http://hslpicker.com/)'
      - name: '**HSLA**'
        details:
          - 'HSL with semi-transparent/opacity.'
          - '*Examples:* `hsla(0, 100%, 100%, .5)`, `hsla(53, 100%, 50%, .7)`, `hsla(167, 38%, 59%, .3)`'
      - name: '**Transparency**'
        details:
          - 'The `transparent` keyword can be used to remove a colour.'
      - name: '**Current colour**'
        details:
          - 'The `currentColor` keyword can be used to capture the `color` of the same element.'
          - '*Example:* `color: red; border-color: currentColor; /* Will be red */`'

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

---
