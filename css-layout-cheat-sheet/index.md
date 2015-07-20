---
layout: cheatsheet
group: web-dev-1

groups:
  - title: 'Layout mechanics'
    items:
      - name: '*Display*'
        details:
          - 'Controls how an element is represented within the flow.'
          - '`display: inline`'
          - '![](display-inline.svg)'
          - '*Allows other elements beside; margin, padding & width don’t work.*'
          - '`display: block`'
          - '![](display-block.svg)'
          - '*Takes up an entire line; margin, padding & width work.*'
          - '`display: inline-block`'
          - '![](display-inline-block.svg)'
          - '*Allows other elements beside; margin, padding & width work. Can create columns, but will force a space between boxes.*'
      - name: '*Float*'
        details:
          - 'Controls whether text is wrapped around the element.'
          - '`float: left|right|none`'
          - '![]()'
          - '*Allows other elements to wrap around the element.*'
          - 'Multiple floats'
          - '![]()'
          - '*Can create columns with boxes touching sides.*'
          - '`clear: left|right|both`'
          - '![]()'
          - '*Force the element below floated elements.*'
          - '`overflow: hidden`'
          - '![]()'
          - '*Use on a parent element to force it to wrap around the floated children—a clearfix.*'
      - name: '*Position*'
        details:
          - 'Controls layering and specific locations within other elements.'
          - '*Examples:* `#heading-1`, `#facebook`, `#top`'


- title: 'Common code'
    items:
      - name: '*Clearfix*'
        details:
          - '*Can be used instead of `overflow: hidden`*'
          - |
            ```css
            .clearfix:before,
            .clearfix:after {
              content: " ";
              display: table;
            }

            .clearfix:after {
              clear: both;
            }
            ```
      - name: '*Border box*'
        details:
          - '*Used to change layout math for width & padding.*'
          - |
            ```css
            html {
              box-sizing: border-box;
            }

            *, *::before, *::after {
              box-sizing: inherit;
            }
            ```
---
