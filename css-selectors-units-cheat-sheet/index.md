---
layout: cheatsheet
group: setup

groups:
  - title: 'Selectors'
    items:
      - name: '``'
        details:
          - ''

  - title: 'Colours'
    items:
      - name: '**Keywords**'
        details:
          - 'Standardized, named colours.'
          - 'Examples: `red`, `white`, `darkorange`, `hotpink`, `limegreen`.'
          - '[Color keywords](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#Color_keywords).'
      - name: '**Hexadecimal**'
        details:
          - 'Hex colours start with a hash: `#`.'
          - 'Three separate numbers: red, green, blue.'
          - 'Examples: `#000000`, `#ffffff`, `#ff3333`, `#b95f48`.'
          - 'Simplify pairs: `#000`, `#fff`, `#f33`.'
      - name: '**RGB**'
        details:
          - 'Specify colours using red, green & blue numbers.'
          - 'Examples: `rgb(255, 255, 255)`, `rgb(255, 0, 0)`, `rgb(124, 65, 99)`.'
      - name: '**RGBA**'
        details:
          - 'RGB with semi-transparent/opacity.'
          - 'Examples: `rgba(0, 0, 0, .5)`, `rgba(255, 0, 0, .75)`, `rgba(124, 65, 99, .8)`.'
      - name: '**HSL**'
        details:
          - 'Specify colours using the hue, saturation, lightness system.'
          - 'Different from Photoshop’s HSB system.'
          - 'Examples: `hsl(0, 100%, 100%)`, `hsl(53, 100%, 50%)`, `hsl(167, 38%, 59%)`.'
          - '[HSL Color Picker](http://hslpicker.com/)'
      - name: '**HSLA**'
        details:
          - 'HSL with semi-transparent/opacity.'
          - 'Examples: `hsla(0, 100%, 100%, .5)`, `hsla(53, 100%, 50%, .7)`, `hsla(167, 38%, 59%, .3)`.'
      - name: '**Transparency**'
        details:
          - 'The `transparent` keyword can be used to remove a colour.'
      - name: '**Current colour**'
        details:
          - 'The `currentColor` keyword can be used to capture the `color` of the same element.'
          - 'Example: `color: red; border-color: currentColor; /* Will be red */`'

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
