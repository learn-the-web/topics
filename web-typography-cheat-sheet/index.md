---
layout: cheatsheet
group: web-dev-1

groups:
  - title: 'Metrics'
    items:
      - name: '`1rem`, `100%`, `16px`'
        details:
          - '**Body copy size** — should *never* be smaller.'
          - '`110%` for large screens.'
          - '`120%` for extra large screens.'
      - name: '`1.3` – `1.5`'
        details:
          - '**Body line-height** — looser on the web.'
          - '`1.3` for small screens.'
          - '`1.4` for medium screens.'
          - '`1.5` for large screens.'
      - name: '`30em` – `40em`'
        details:
          - '**Body maximum line-length.**'
          - 'Shorter on small screens is okay.'

  - title: 'Units'
    items:
      - name: '`rem`'
        details:
          - 'Based on the font-size set in the `html` element.'
          - '`1.5rem` is 1.5 × the `html` element’s font size.'
      - name: '`em`'
        details:
          - 'Based on the font-size of the parent (or current element).'
          - '`1em` is 1 × the parent element’s size.'
          - '`0.5em` is 0.5 × the parent element’s size.'
      - name: '`%`'
        details:
          - '*Percentage*'
          - 'A percentage of the font-size of the parent element.'
          - '`80%` is to 80% the size of the parent element.'
      - name: '`vh`'
        details:
          - '*Viewport height*'
          - 'Allows you to change the type size based on the height of the window.'
      - name: '`vw`'
        details:
          - '*Viewport width*'
          - 'Allows you to change the type size based on the width of the window.'
      - name: '`px`'
        details:
          - '*CSS pixels*—different sizes for every device.'
          - '`16px` is exactly 16 pixels in all situations.'
          - '**Avoid using pixels for font sizes unless absolutely necessary.**'

  - title: 'Properties'
    items:
      - name: '`color`'
        details:
          - 'The colour of the text.'
          - '*Example:* `color: red;`'
          - '[☛ See CSS colour reference.](/topics/css-selectors-units-cheat-sheet/#colours)'
      - name: '`font-family`'
        details:
          - 'Change the typeface of the text.'
          - 'Put quotes around typefaces with spaces in their names.'
          - '*Always provide a fallback typeface.*'
          - '*Web safe fonts:* Georgia, Arial, Verdana, Times, Comic Sans, Courier.'
          - '*Example:* `font-family: "Open Sans", sans-serif;`'
      - name: '`font-size`'
        details:
          - 'Change the size of the text.'
          - 'Prefer `rem` or `em` units.'
          - '*Example:* `font-size: 1.5rem;`'
      - name: '`font-weight`'
        details:
          - 'Change the thickness of the text.'
          - '`bold`, `normal`, number: `400`, `700`, etc.'
          - '*Example:* `font-weight: bold;`'
      - name: '`font-style`'
        details:
          - 'Change the slanting of the text.'
          - '`italic`, `normal`'
          - '*Example:* `font-style: italic;`'
      - name: '`line-height`'
        details:
          - 'Adjust the space a line takes up, similar to leading.'
          - 'Set in a number, a multiplier of the font size.'
          - '*Example:* `line-height: 1.4;`'
      - name: '`text-align`'
        details:
          - 'Adjust the position of the text within its parent.'
          - '`left`, `right`, `center`, `justify`'
          - '*Example:* `text-align: center;`'
      - name: '`text-decoration`'
        details:
          - 'Add or remove lines on the text.'
          - '`none`, `underline`, `line-through`, `overline`'
          - '*Example:* `text-decoration: underline;`'
      - name: '`text-transform`'
        details:
          - 'Change the capitalization of the text.'
          - '`uppercase`, `lowercase`, `capitalize`'
          - '*Example:* `text-transform: uppercase;`'
      - name: '`text-indent`'
        details:
          - 'Indent the first line of text.'
          - 'Set the number in ems.'
          - '*Example:* `text-indent: .8em;`'
      - name: '`text-shadow`'
        details:
          - 'Add a drop shadow to text.'
          - 'Needs four properties: *horizontal offset*, *vertical offset*, *blur radius*, *colour*.'
          - 'Use a comma after the colour to add more than one shadow.'
          - '*Example:* `text-shadow: 2px 2px 5px rgba(0,0,0,.5);`'
      - name: '`text-overflow`'
        details:
          - 'Determine what happens to the text if it’s too wide for its box.'
          - 'Often requires `overflow: hidden;` to also be used.'
          - '`ellipsis`, `clip`, custom: `"."`'
          - '*Example:* `text-overflow: ellipsis;`'
      - name: '`list-style-type`'
        details:
          - 'Control the style of bullets on a list.'
          - '`none`, `circle`, `disc`, `square`, `decimal`, `lower-alpha`, `lower-roman`, `lower-greek`'
          - '*Example:* `list-style-type: square;`'

  - title: 'Experimental properties'
    note: 'These properties may not work in all browser and may have a major performance impact.'
    items:
      - name: '`hyphens`'
        details:
          - 'Control if the text will be hyphenated.'
          - 'Usually requires `text-align: justify`.'
          - '`none`, `auto`'
          - '*Example:* `hyphens: auto;`.'
      - name: '`font-kerning`'
        details:
          - 'Control a font’s built-in kerning metrics.'
          - '`none`, `normal`, `auto`'
          - '*Example:* `font-kerning: auto;`.'
      - name: '`font-variant-ligatures`'
        details:
          - 'Control whether ligatures are used or not.'
          - '`none`, `normal`, specific: `common-ligatures`, `contextual`, etc.'
          - '*Example:* `font-variant-ligatures: normal;`.'
      - name: '`font-variant-numeric`'
        details:
          - 'Enable/disabled alternative glyphs for numbers & fractions.'
          - '`normal`, `ordinal`, `slashed-zero`, `oldstyle-nums`, `tabular-nums`, etc.'
          - '*Example:* `font-variant-numeric: oldstyle-nums;`.'
      - name: '`font-variant-caps`'
        details:
          - 'Control whether small caps are used or not.'
          - '`normal`, `small-caps`'
          - '*Example:* `font-variant-caps: small-caps;`.'
      - name: '`text-rendering`'
        details:
          - 'Controls a bunch of the `font-variant` properties automatically.'
          - '**Has extreme performance issues.**'
          - '*Example:* `text-rendering: optimizeLegibility;`.'

  - title: 'Keyboard shortcuts'
    items:
      - name: '`“ ”`'
        details:
          - '*Double curly quote*.'
          - '`“`— Mac:`⌥[`'
          - '`”`— Mac:`⌥⇧]`'
      - name: "`‘ ’`"
        details:
          - '*Single curly quote*, *apostrophe*.'
          - '`‘`— Mac:`⌥]`'
          - '`’`— Mac:`⌥⇧]`'
      - name: '`“ ”`'
        details:
          - '*Double guillemet*.'
          - '`«`— Mac:`⌥\`'
          - '`»`— Mac:`⌥⇧\`'
      - name: "`‘ ’`"
        details:
          - '*Single guillemet*.'
          - '`‹`— Mac:`⌥3`'
          - '`›`— Mac:`⌥⇧4`'
      - name: '`–`'
        details:
          - '*En-dash*.'
          - 'Mac:`⌥-`'
      - name: '`—`'
        details:
          - '*Em-dash*.'
          - 'Mac:`⌥⇧-`'
      - name: '`•`'
        details:
          - '*Bullet*.'
          - 'Mac:`⌥8`'
      - name: '`·`'
        details:
          - '*Middle dot*.'
          - 'Mac:`⌥⇧9`'
      - name: '`°`'
        details:
          - '*Degree*.'
          - 'Mac:`⌥⇧8`'
      - name: '`…`'
        details:
          - '*Ellipsis*.'
          - 'Mac:`⌥;`'
      - name: '`№`'
        details:
          - '*Numero*.'
          - 'Mac:`⌥⇧;`'
      - name: '`¶`'
        details:
          - '*Pilcrow*.'
          - 'Mac:`⌥7;`'
      - name: '`‡`'
        details:
          - '*Double dagger*.'
          - 'Mac:`⌥⇧7;`'
      - name: '`¢`'
        details:
          - '*Cents*.'
          - 'Mac:`⌥4`'
      - name: '`§`'
        details:
          - '*Section*.'
          - 'Mac:`⌥5`'
      - name: '`©`'
        details:
          - '*Copyright*.'
          - 'Mac:`⌥G`'

---
