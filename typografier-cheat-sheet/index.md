---
layout: cheatsheet
group: web-dev-2

groups:
  - title: 'Font sizes'
    items:
      - name: '`.yotta`'
        details:
          - 'Two sizes larger than the `<h1>`.'
      - name: '`.zetta`'
        details:
          - 'One size larger than the `<h1>`.'
      - name: '`.exa`, `<h1>`'
        details:
          - 'Same size as the `<h1>`.'
          - 'Five sizes larger than body copy.'
      - name: '`.peta`, `<h2>`'
        details:
          - 'Four sizes larger than body copy.'
      - name: '`.tera`, `<h3>`'
        details:
          - 'Three sizes larger than body copy.'
      - name: '`.giga`, `<h4>`'
        details:
          - 'Two sizes larger than body copy.'
      - name: '`.mega`, `<h5>`'
        details:
          - 'One size large than body copy.'
      - name: '`.kilo`, `<h6>`, `<p>`, *default*'
        details:
          - 'The default font size, body copy.'
      - name: '`.milli`, `<small>`'
        details:
          - 'One size small than the body copy.'
      - name: '`.micro`'
        details:
          - 'Two sizes smaller than the body copy.'

  - title: 'Spacing'
    items:
      - name: '`.push`'
        details:
          - 'Adds consistent margin to the bottom.'
          - '*Try to avoid using top margins for consistency.*'
      - name: '`.push-none`, `.push-0`'
        details:
          - 'Remove the bottom margin.'
      - name: '`.push-2`, `.push-1-2`, `.push-1-4`'
        details:
          - 'Add differing sizes of margin to the bottom.'
          - 'Available as fully written out versions: `.push-double`, `.push-half`, `.push-quarter`.'
      - name: '`.gutter`,`.gutter-2`, `.gutter-1-2`, `.gutter-1-4`'
        details:
          - 'Adds padding to left and right sides.'
          - 'Available as fully written out versions: `.gutter-double`, `.gutter-half`, `.gutter-quarter`.'
      - name: '`.island`,`.island-2`, `.island-1-2`, `.island-1-4`'
        details:
          - 'Adds padding to all four sides.'
          - 'Available as fully written out versions: `.island-double`, `.island-half`, `.island-quarter`.'
      - name: '`.pad-t`,`.pad-t-2`, `.pad-t-1-2`, `.pad-t-1-4`'
        details:
          - 'Adds padding to top of the box.'
          - 'Available as fully written out versions: `.pad-top`, `.pad-top-double`, `.pad-top-half`, `.pad-top-quarter`.'
      - name: '`.pad-b`,`.pad-b-2`, `.pad-b-1-2`, `.pad-b-1-4`'
        details:
          - 'Adds padding to bottom of the box.'
          - 'Available as fully written out versions: `.pad-bottom`, `.pad-bottom-double`, `.pad-bottom-half`, `.pad-bottom-quarter`.'

  - title: 'Utilities'
    items:
      - name: '`.text-left`, `.text-right`, `.text-center`'
        details:
          - 'Text alignment classes.'
          - '*These are brute force and not responsive, so use only when it will always need that alignment.*'
      - name: '`.normal`, `.bold`, `.italic`'
        details:
          - 'Font style and weight classes.'
          - '*These are brute force and not responsive, so use only when it will always need that style or weight.*'

---
