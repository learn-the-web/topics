---
layout: cheatsheet
group: web-dev-1

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
          - 'Controls layering and specific locations within other elements.'
          - '*Examples:* `#heading-1`, `#facebook`, `#top`'


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
      - name: '*Clearfix*'
        details:
          - 'Can be used instead of `overflow: hidden`'
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
---
