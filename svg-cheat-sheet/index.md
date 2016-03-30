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
      - name: '*View box*'
        details:
          - 'Controls the artboard of the SVG—like in Illustrator.'
          - |
            ```xml
            <svg viewBox="0 0 256 256"></svg>
            ```
          - 'Graphics that exist outside the viewbox will be cropped or changed—based on `preserveAspectRatio`'
      - name: '*Preserve aspect ratio*'
        details:
          - 'Controls how the graphics inside the artboard are adjusted when the SVG’s width/height are changed.'
          - |
            ```xml
            <svg preserveAspectRatio="xMidYMid"></svg>
            ```
          - '`none`—stretch the graphic to fill the space.'
          - '`xMidYMid`—uniform scaling, aligning to the middle.'
          - '`xMinYMin`—uniform scaling, aligning to the top-left.'
          - '`xMaxYMax`—uniform scaling, aligning to the bottom-right.'
          - '*And everything else in between: think of the viewBox having 9 different anchor points for the graphic.*'

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
            <rect x="0" y="0" width="256" height="64" rx="5" ry="5" />
            ```
          - '`x`—the top left corner’s “x” coordinate.'
          - '`y`—the top left corder’s “y” coordinate.'
          - '`width`—the horizontal size of the rectangle.'
          - '`height`—the vertical size of the rectangle.'
          - '`rx`—for adding rounded corners; the horizontal radius of the rounding circle.'
          - '`ry`—for adding rounded corners; the vertical radius of the rounding circle.'
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
      - name: '*Paths*'
        details:
          - 'Paths, like Illustrator, multiple anchors with handles.'
          - |
            ```xml
            <path d="M100,160 Q128,190 156,160" />
            ```
          - '`d`—full of points and coordinates to control the path and its handles.'
          - '*Generally this is written by a program, like Illustrator, not written by hand.*'
          - '[See the `path` documentation for more details](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/d).'

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
      - name: '*Symbols*'
        details:
          - 'Creating reusable graphics for within the SVG—great for making icons.'
          - |
            ```xml
            <symbol id="icon-smiley" viewBox="0 0 256 256">
              <circle cx="128" cy="128" r="120" />
              <circle cx="100" cy="104" r="12" />
              <circle cx="156" cy="104" r="12" />
              <path d="M100,160 Q128,190 156,160" />
              <rect x="97" y="66" width="6" height="32" rx="4" ry="4" />
              <rect x="153" y="66" width="6" height="32" rx="4" ry="4" />
            </symbol>
            ```
      - name: '*Using symbols*'
        details:
          - 'The `<use>` is how we use previously defined symbols.'
          - |
            ```xml
            <use xlink:href="#icon-smiley" />
            ```
      - name: '*Definitions*'
        details:
          - 'Create shapes and graphics that won’t be visible until used in other places like gradients, paths for text, masks, etc.'
          - |
            ```xml
            <defs>
              <path id="arc" d="M100,160 Q128,190 156,160" />
            </defs>
            ```

  - title: 'Styling shapes'
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
          - '*Can be put on any element including the `<svg>` element.*'
      - name: '*Opacity*'
        details:
          - 'Same as CSS.'
          - |
            ```xml
            <circle opacity=".5" fill="orange" cx="100" cy="100" r="100" />
            ```
      - name: '*Gradients*'
        details:
          - |
            ```xml
            <defs>
              <linearGradient id="the-gradient">
                <stop offset="0%" stop-color="orange" />
                <stop offset="100%" stop-color="red" />
              </linearGradient>
            </defs>
            <circle fill="url(#the-gradient)" cx="100" cy="100" r="100" />
            ```

  - title: 'Styling strokes'
    items:
      - name: '*Stroke*'
        details:
          - 'Adds a line around the outside of a shape or along a path.'
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
      - name: '*Stroke opacity*'
        details:
          - |
            ```xml
            <circle stroke-opacity=".5" stroke="orange" cx="100" cy="100" r="100" />
            ```
          - '`stroke-opacity`—used to set the transparency of the stroke itself.'
      - name: '*Stroke line cap*'
        details:
          - |
            ```xml
            <circle stroke-linecap="round" stroke="orange" cx="100" cy="100" r="100" />
            ```
          - '`stroke-linecap`—used to control the end of strokes: `butt`, `round`, `square`.'
      - name: '*Stroke line join*'
        details:
          - |
            ```xml
            <circle stroke-linejoin="bevel" stroke="orange" cx="100" cy="100" r="100" />
            ```
          - '`stroke-linejoin`—used to control the corner style of strokes: `miter`, `round`, `bevel`.'
      - name: '*Stroke miter limit*'
        details:
          - |
            ```xml
            <circle stroke-miterlimit="4" stroke="orange" cx="100" cy="100" r="100" />
            ```
          - '`stroke-miterlimit`—when two stroke corners meet they can sometimes make very long pointy triangles—this controls how long they are.'
      - name: '*Line dashes*'
        details:
          - |
            ```xml
            <line stroke-dasharray="4,6" x1="0" y1="0" x2="256" y2="256" />
            ```
          - '`stroke-dasharray`—creates dashed lines for strokes'
          - 'The `4,6` means: “4 pixel dash followed by 6 pixel space.”'

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
              <tspan fill="limegreen">not</tspan>
              a dinosaur.
            </text>
            ```
          - 'The `tspan` element is used to surround words inside `<text>`'
          - 'It has the same purpose as HTML’s `<span>` element.'
      - name: '*Text adjustments*'
        details:
          - |
            ```xml
            <text x="0" y="0">
              Dimetrodon is
              <tspan dy="-30">not</tspan>
              a dinosaur.
            </text>
            ```
          - '`dx`—adjust the text horizontally in relation to where it is currently.'
          - '`dy`—adjust the text vertically in relation to where it is currently.'
      - name: '*Text on a path*'
        details:
          - 'Make text follow along with a path.'
          - |
            ```xml
            <defs>
              <path id="arc" d="M100,160 Q128,190 156,160" />
            </defs>
            <textPath xlink:href="#arc">Dinosaurs!</textPath>
            ```

  - title: 'Styling text'
    items:
      - name: '*Font family*'
        details:
          - 'Same as CSS.'
          - |
            ```xml
            <text font-family="Georgia, serif">Dinosaurs!</text>
            ```
      - name: '*Font size*'
        details:
          - 'Same as CSS.'
          - |
            ```xml
            <text font-size="1.5rem">Dinosaurs!</text>
            ```
      - name: '*Font weight*'
        details:
          - 'Same as CSS.'
          - |
            ```xml
            <text font-weight="bold">Dinosaurs!</text>
            ```
      - name: '*Font style*'
        details:
          - 'Same as CSS.'
          - |
            ```xml
            <text font-style="italic">Dinosaurs!</text>
            ```
      - name: '*Text decoration*'
        details:
          - 'Same as CSS.'
          - |
            ```xml
            <text text-decoration="none">Dinosaurs!</text>
            ```
      - name: '*Letter spacing*'
        details:
          - 'Same as CSS.'
          - |
            ```xml
            <text letter-spacing="30">Dinosaurs!</text>
            ```
      - name: '*Text length*'
        details:
          - 'Space out the letters to fill a specific width.'
          - |
            ```xml
            <text textLength="900">Dinosaurs!</text>
            ```
      - name: '*Gradients*'
        details:
          - 'Same as gradients on shapes.'
          - |
            ```xml
            <defs>
              <linearGradient id="the-gradient">
                <stop offset="0%" stop-color="limegreen" />
                <stop offset="100%" stop-color="green" />
              </linearGradient>
            </defs>
            <text fill="url(#the-gradient)">Dinosaurs!</text>
            ```

  - title: 'Styling with CSS'
    items:
      - name: '*Styling shapes*'
        details:
          - 'Many of the styling attributes listed above for shapes & lines can also be used in CSS.'
          - |
            ```xml
            <circle class="face" cx="128" cy="128" r="120" />
            ```
          - |
            ```css
            .face {
              fill: yellow;
              stroke: #000;
              stroke-width: 6px;
              stroke-dasharray: 4,4;
            }
            ```
      - name: '*Styling text*'
        details:
          - 'Many of the styling attributes listed above for text can also be used in CSS.'
          - |
            ```xml
            <text class="dinos">Dinosaurs!</text>
            ```
          - |
            ```css
            .dinos {
              font-family: Georgia, serif;
              font-style: italic;
              font-size: 1.5rem;
            }
            ```
      - name: '*Styling effects*'
        details:
          - 'Many of the effect related attributes can also be styled in CSS.'
          - |
            ```xml
            <rect class="box" x="0" y="0" width="256" height="64" />
            ```
          - |
            ```css
            .box {
              fill: limegreen;
              transform: rotate(45deg);
              transition: all .25s linear;
            }

            .box:hover {
              fill: orange;
            }
            ```

---
