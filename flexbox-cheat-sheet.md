---
layout: cheatsheet
title: "Flexbox cheat sheet"
tags: "css advanced layout flexbox align content justify vertical cheat sheet"
desc: "A cheat sheet covering all the properties used in flexbox and how they work."

groups:
  - title: 'Enabling'
    items:
      - name: '`display: flex`'
        details:
          - 'Turns a parent element into a flex container-all child elements will become part of the flex flow.'
          - 'Forces the parent element into a `display: block`-like state where it takes up an entire row.'
          - |
            ```css
            .dinos {
              display: flex;
            }
            ```
          - '**Affects all the child elements inside this parent container element.**'
      - name: '`display: inline-flex`'
        details:
          - 'Same as `flex` but allows the parent element to be `display: inline-block`'
          - |
            ```css
            .dinos {
              display: inline-flex;
            }
            ```
          - '**Affects all the child elements inside this parent container element.**'
      - name: '**Affects child elements**'
        details:
          - 'The flexbox code is triggered on the parent element, but affects all of the child elements.'
          - '![](display-flex.png)'

  - title: 'Orientation'
    items:
      - name: '`flex-direction`'
        details:
          - '`row`, `row-reverse`, `column`, `column-reverse`'
          - 'Choose the direction of the flexbox children, horizontally (`row`) or vertically (`column`).'
          - 'The `*-reverse` options will reorder the children in the opposite order they’re written in HTML.'
          - '**`row` is the default.**'
          - |
            ```css
            .dinos {
              flex-direction: row;
            }
            ```
          - '![](flex-direction.png)'
      - name: '`flex-wrap`'
        details:
          - '`wrap` , `nowrap`'
          - 'Whether to allow the child elements to wrap to another line or force them all on a single line.'
          - '**`nowrap` is the default.**'
          - |
            ```css
            .dinos {
              flex-wrap: nowrap;
            }
            ```
          - '![](flex-wrap.png)'
      - name: '`order`'
        details:
          - 'Reorder a single child element within the flex flow. *Negative numbers allowed.*'
          - |
            ```css
            .stega {
              /* Move an element to the start */
              order: -1;
            }
            .bronto {
              /* Move an element to the end */
              order: 1000;
            }
            ```
          - '![](order.png)'

  - title: 'Alignment'
    items:
      - name: '`justify-content`'
        details:
          - '`flex-start`, `flex-end`, `center`, `space-around`, `space-between`'
          - 'Control how the elements are spaced within their parent flex container.'
          - |
            ```css
            .dinos {
              /* Move all elements to the center */
              justify-content: center;
            }
            .dinos {
              /* Make elements touch the edge and space evenly between */
              justify-content: space-between;
            }
            ```
          - '![](justify-content.png)'
      - name: '`align-items`'
        details:
          - '`flex-start`, `flex-end`, `center`, `stretch`'
          - 'Control how elements are aligned in the opposite direction of their justification.'
          - |
            ```css
            .dinos {
              /* Force all elements to be the same height */
              flex-direction: row;
              align-items: stretch;
            }
            ```
          - '**`align-self`** — is a similar property, but allows you to target a single child element, instead of all of the children.'
          - |
            ```css
            .stega {
              /* Force .stega to be at the bottom */
              flex-direction: row;
              align-self: flex-end;
            }
            ```
          - '![](align-items.png)'

      - name: '`align-content`'
        details:
          - '`flex-start`, `flex-end`, `center`, `space-around`, `space-between`, `stretch`'
          - 'How to align the grouping of **wrapped** flex children—only works with `flex-wrap: wrap`'
          - |
            ```css
            .dinos {
              /* Spread the wrapped children to fill their parent */
              align-content: space-between;
            }
            ```
          - '![](align-content.png)'

  - title: 'Flexibility'
    items:
      - name: '`flex-basis`'
        details:
          - 'Similar to `width` and `height` but not a guaranteed size: it can adjust up or down within the flex-parent to make sure the elements fit. It’s more like a suggestion.'
          - |
            ```css
            .stego {
              /* Same size as the content */
              flex-basis: content;
            }
            .bronto {
              /* 45% the width of the parent */
              flex-basis: 45%;
            }
            ```
          - '![](flex-basis.png)'
      - name: '`flex-grow`'
        details:
          - 'A unitless number that defines how much of the leftover space this element should be allotted.'
          - 'Chunks the leftover space and allots based on this multiplier.'
          - 'Without `flex-grow` all elements will be allotted the same amount of space.'
          - |
            ```css
            .bronto {
              /* Gets 1 piece of the space */
              flex-grow: 1;
            }
            .stego {
              /* Gets 2 pieces of the space */
              flex-grow: 2;
            }
            ```
          - '![](flex-grow.png)'
      - name: '`flex-shrink`'
        details:
          - 'Opposite to `flex-grow`: defines how much space it can shrink.'
          - 'If there isn’t enough space available the element will remove allotments against this multiplier.'
          - |
            ```css
            .tricera {
              flex-shrink: 2;
            }
            ```
          - '![](flex-shrink.png)'
---
