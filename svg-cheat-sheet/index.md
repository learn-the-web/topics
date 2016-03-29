---
layout: cheatsheet
group: web-dev-3

groups:
  - title: 'Setup'
    items:
      - name: '*Inside *.svg files*'
        details:
          - |
            ```xml
            <svg width="256" height="256" viewBox="0 0 256 256" xmlns="http://www.w3.org/2000/svg">
              <!-- SVG code goes in here -->
            </svg>
            ```
          - 'The `xmlns` attribute is critical.'
          - '`width` & `height` denote the dimensions of the SVG graphic—they’re very important for browser compatability.'
          - '`viewBox` defines an artboard, a cropping area, following this syntax: `viewBox="x y width height"`'
      - name: '*Embedded in HTML files*'
        details:
          - |
            ```xml
            <body>
              <svg width="256" height="256" viewBox="0 0 256 256">
                <!-- SVG code goes in here -->
              </svg>
            </body>
            ```
          - 'The `xmlns` attribute is not necessary.'
      - name: '*Embedded in CSS files*'
        details:
          - |
            ```css
            background-image: url("data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='256' height='256' viewBox='0 0 256 256'%3E%3Cpath d='M201.5 24v31.4h31.7V234H55.5v-30H22.7V24h178.8zm-11.8 11.4H34.4v157.3h155.2V35.4z'/%3E%3C/svg%3E");
            ```
          - 'Start every URL with the DataURL scheme: `data:image/svg+xml;charset=utf8,`'
          - 'The `<` must be escaped with `%3C`'
          - 'The `%3E` must be escaped with `%3E`'
          - 'The `#` must be escaped with `%23`'
          - The `"` must be replaced with `'`

  - title: 'Shapes'
    items:
      - name: '*Circles*'
        details:
          - |
            ```xml
            <circle cx="100" cy="100" r="100" />
            ```
          - '`cx`—the centre “x” coordinate.'
          - '`cy`—the centre “y” coordinate.'
          - '`r`—the radius of the circle (half its width).'
      - name: '*Ellipses*'
        details:
          - |
            ```xml
            <ellipse cx="100" cy="100" rx="100" ry="50" />
            ```
          - '`cx`—the centre “x” coordinate.'
          - '`cy`—the centre “y” coordinate.'
          - '`rx`—the horizontal radius of the oval (half its width).'
          - '`ry`—the verical radius of the oval (half its height).'
      - name: '*Rectangles*'
        details:
          - |
            ```xml
            <rect x="0" y="0" width="256" height="64" />
            ```
          - '`x`—the top left corner’s “x” coordinate.'
          - '`y`—the top left corder’s “y” coordinate.'
          - '`width`—the horizontal size of the rectangle.'
          - '`height`—the vertical size of the rectangle.'
      - name: '*Polygons*'
        details:
          - 'A non-rectangular shape.'
          - |
            ```xml
            <!-- A triangle -->
            <polygon points="128,0 256,256 0,256" />
            <!-- A hexagon -->
            <polygon points="60,20 100,40 100,80 60,100 20,80 20,40" />
            ```
          - '`points`—defines the coordinates of each of the corners of the shape—the format is: `x,y x,y…`'
      - name: '*Lines*'
        details:
          - 'Lines with only a start point and an end point.'
          - |
            ```xml
            <line x1="0" y1="0" x2="256" y2="256" />
            ```
          - '`x1`—the line’s starting “x” coordinate.'
          - '`y1`—the line’s starting “y” coordinate.'
          - '`x2`—the line’s ending “x” coordinate.'
          - '`y2`—the line’s ending “y” coordinate.'
      - name: '*Polylines*'
        details:
          - 'Multi-point lines.'
          - |
            ```xml
            <polyline points="0,256 50,150 100,100 150,50" />
            ```
          - '`points`—defines the coordinates of each position of the line—the format is: `x,y x,y…`'
      # - name: '*Paths*'
        # details:
          # - ''

  - title: 'Grouping & naming'
    items:
      - name: '*Grouping elements*'
        details:
          - 'Use the `<g>` tag to group elements together.'
          - |
            ```xml
              <svg width="256" height="256" viewBox="0 0 256 256">
                <g>
                  <circle cx="100" cy="100" r="100" />
                  <rect x="0" y="0" width="256" height="64" />
                  <polyline points="0,256 50,150 100,100 150,50" />
                </g>
              </svg>
            ```
      - name: '*Classes*'
        details:
          - 'The `class` attribute can be added to any element.'
          - |
            ```xml
              <svg class="dino" width="256" height="256" viewBox="0 0 256 256">
                <g class="head">
                  <circle class="eye" cx="100" cy="100" r="100" />
                  <rect class="nose" x="0" y="0" width="256" height="64" />
                </g>
              </svg>
            ```
      - name: '*IDs*'
        details:
          - 'The `ID` attribute can be added to any element.'
          - |
            ```xml
              <svg id="dino" width="256" height="256" viewBox="0 0 256 256">
                <g id="head">
                  <circle id="eye" cx="100" cy="100" r="100" />
                  <rect id="nose" x="0" y="0" width="256" height="64" />
                </g>
              </svg>
            ```
          - '*Remember that the ID is unique: it can only be used once per SVG graphic & once per HTML file.*'

  - title: 'Styling'
    items:
      - name: '*Fill*'
        details:
          - |
            ```xml
            <circle fill="orange" cx="100" cy="100" r="100" />
            <g fill="midnightblue">
              <circle cx="100" cy="100" r="100" />
            </g>
            ```
          - '`fill`—used to set the color of a shape. Can use any colour format: keywords, `#` hex, `rgb()`, `rgba()`'
          - 'Can be put on any element including the `<svg>` element.'
      - name: '*Stroke*'
        details:
          - |
            ```xml
            <circle stroke="orange" cx="100" cy="100" r="100" />
            ```
          - '`stroke`—used to set the color of a stroke. Can be any colour format: keywords, `#` hex, `rgb()`, `rgba()`'
      - name: '*Stroke width*'
        details:
          - |
            ```xml
            <circle stroke-width="10" stroke="orange" cx="100" cy="100" r="100" />
            ```
          - '`stroke-width`—used to set the thickness of the stroke.'

  - title: 'Text'
    items:
      - name: '*Text blocks*'
        details:
          - |
            ```xml
            <text x="128" y="128" text-anchor="middle">Dinosaurs!</text>
            ```
          - '`x`—the “x” coordinate of the text’s anchor point.'
          - '`y`—the “y” coordinate of the text’s anchor point.'
          - '`text-anchor`—the text alignment: `start` (left), `middle` (centre), `end` (right).'
      - name: '*Inside text*'
        details:
          - |
            ```xml
            <text x="0" y="0">
              Dimetrodon is
              <tspan font-style="italic">not</tspan>
              a dinosaur.
            </text>
            ```
          - 'The `tspan` element is used to surround words inside `<text>`'
          - 'It has the same purpose as HTML’s `<span>` element.'

---
