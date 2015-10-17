---
layout: cheatsheet
group: web-dev-2

groups:
  - title: 'Making a grid'
    items:
      - name: '`.grid`'
        details:
          - 'Wraps around a whole grid row.'
          - '*Can only have elements with the `.unit` class immediately inside.*'
      - name: '`.unit`'
        details:
          - 'Defines an element as being a single grid module.'
          - '*Can only be immediately inside a `.grid` element.*'
      - name: '*Example grid setup*'
        details:
          - |
            ```html
            <div class="grid">
              <div class="unit">…</div>
              <div class="unit">…</div>
            </div>
            ```
          - '*Nothing can be outside of `.unit` when using grids.*'

  - title: 'Grid unit alignment'
    items:
      - name: '`.grid-bottom`'
        details:
          - 'Aligns all the units to the bottom of the grid row.'
      - name: '`.grid-middle`'
        details:
          - 'Vertically centers all the units inside a grid row.'
      - name: '`.grid-stretch`'
        details:
          - 'Forces all the unit elements to be the same height.'

  - title: 'Units'
    items:
      - name: '`.unit-[size]-1`, `.[size]-1`'
        details:
          - 'Unit takes up one whole row.'
      - name: '`.unit-[size]-1-2`, `.[size]-1-2`'
        details:
          - 'Unit takes up half of the available width in the row.'
      - name: '`.unit-[size]-1-3`, `.[size]-1-3`'
        details:
          - 'Unit takes up one-third of the available width in the row.'
      - name: '`.unit-[size]-2-3`, `.[size]-2-3`'
        details:
          - 'Unit takes up two-thirds of the available width in the row.'

  - title: 'Unit size examples'
    note 'These are just samples of what to expect for certain max column numbers.'
    items:
      - name: '*3-column grid sizes*'
        details:
          - '`.unit-xs-1`'
          - '`.unit-xs-1-2`'
          - '`.unit-xs-1-3`'
          - '`.unit-xs-2-3`'
      - name: '*4-column grid sizes*'
        details:
          - '`.unit-m-1`'
          - '`.unit-m-1-2`'
          - '`.unit-m-1-3`'
          - '`.unit-m-2-3`'
          - '`.unit-m-1-4`'
          - '`.unit-m-3-4`'
          - '*Fractions are simplified, so <sup>2</sup>/<sub>4</sub> is <sup>1</sup>/<sub>2</sub>.*'
      - name: '*6-column grid sizes*'
        details:
          - '`.unit-l-1`'
          - '`.unit-l-1-2`'
          - '`.unit-l-1-3`'
          - '`.unit-l-2-3`'
          - '`.unit-l-1-4`'
          - '`.unit-l-3-4`'
          - '`.unit-l-1-5`'
          - '`.unit-l-2-5`'
          - '`.unit-l-3-5`'
          - '`.unit-l-4-5`'
          - '`.unit-l-1-6`'
          - '`.unit-l-5-6`'
          - '*Fractions are simplified, so <sup>3</sup>/<sub>6</sub> is <sup>1</sup>/<sub>2</sub>.*'

  - title: 'Unit utilities'
    items:
      - name: '`.unit-[size]-hidden`'
        details:
          - 'Allows a unit to be hidden on specific screens sizes.'
          - 'e.g. `.unit-xs-hidden`'
      - name: '`.unit-[size]-centered`'
        details:
          - 'Allows a unit to be centered horizontally on specific screen sizes.'
          - 'e.g. `.unit-m-centered`'
      - name: '`.unit-offset-[size]-1-2`'
        details:
          - 'Makes empty space to the left of the unit by the specified amount.'
          - 'There are offset sizes available for every unit width.'
      - name: '`.unit-push-[size]-1-2`'
        details:
          - 'Pushes the unit to the right, to change order.'
          - 'There are push sizes available for every unit width.'
      - name: '`.unit-pull-[size]-1-2`'
        details:
          - 'Pulls the unit to the left, to change order.'
          - 'There are pull sizes available for every unit width.'
      - name: '`.unit-content-distribute`'
        details:
          - 'Makes the content distribute, the top of the unit’s content will align, the bottom content will align.'
          - 'The content in the center will distribute its surrounding space evenly.'
      - name: '`.content-fill`'
        details:
          - 'When using distribute, can cause a chunk of content to stretch vertically.'
          - 'Added to an element *inside* a unit—*will not work added directly to a `.unit`.*'

  - title: 'Example solutions'
    items:
      - name: '*Grids inside grids*'
        details:
          - 'In order to make certain layouts, sometimes grids need to be put inside other grids.'
          - '![](grids-inside-grids.svg)'
          - |
            ```html
            <div class="grid">
              <div class="unit m-1-2 l-1-2">

                <!-- Placing a grid inside another grid gives extra flexibility for certain layouts -->
                <div class="grid">
                  <div class="unit m-1 l-1-2">Unit 1</div>
                  <div class="unit m-1 l-1-2">Unit 2</div>
                </div>

              </div>
              <div class="unit m-1-2 l-1-2">

                <div class="grid">
                  <div class="unit m-1 l-1-2">Unit 3</div>
                  <div class="unit m-1 l-1-2">Unit 4</div>
                </div>

              </div>
            </div>
            ```
      - name: '*Aligning units to the middle*'
        details:
          - 'Using the `.grid-middle` class, we can align the units to the middle of each other.'
          - '![](grid-middle.svg)'
          - |
            ```html
            <div class="grid grid-middle">
              <div class="unit">Unit 1</div>
              <div class="unit">Unit 2</div>
              <div class="unit">Unit 3</div>
            </div>
            ```
          - 'There’s also `.grid-bottom` to align all the units to the bottom.'
          - '![](grid-bottom.svg)'
          - |
            ```html
            <div class="grid grid-bottom">
              ⋮
            </div>
            ```
      - name: '*Distributing content within units*'
        details:
          - 'If the content inside units is different lengths, you can distribute it to align both the top and bottom.'
          - '![](grid-distribute.svg)'
          - |
            ```html
            <div class="grid grid-stretch">
              <div class="unit unit-content-distribute">
                <h2>Unit 1</h2>
                <p class="content-fill">Lorem ipsum dolor sit amet.</p>
                <a href="…">Go!</a>
              </div>
              <div class="unit unit-content-distribute">
                <h2>Unit 2</h2>
                <p class="content-fill">Lorem ipsum dolor sit amet, consectetuer adipiscing elit.</p>
                <a href="…">Don’t go!</a>
              </div>
            </div>
            ```
      - name: '*Hiding elements on certain screens*'
        details:
          - 'Using the `hidden` classes, we can hide specific units on specific screen sizes.'
          - '![](grid-hidden.svg)'
          - |
            ```html
            <div class="grid">
              <div class="unit s-1-4 l-1-4">Unit 1</div>
              <div class="unit unit-s-hidden l-1-4">Unit 2</div>
              <div class="unit s-1-4 l-1-4">Unit 3</div>
              <div class="unit unit-s-hidden l-1-4">Unit 4</div>
            </div>
            ```
      - name: '*Using offsets to create open areas*'
        details:
          - 'If you want to create extra whitespace beside units you can use the `offset` classes.'
          - '![](grid-offset.svg)'
          - |
            ```html
            <div class="grid">
              <div class="unit l-1-2">Unit 1</div>
              <div class="unit l-1-2">Unit 2</div>
              <div class="unit l-1-4 unit-offset-l-1-4">Unit 3</div>
              <div class="unit l-1-2">Unit 4</div>
            </div>
            ```
      - name: '*Reordering elements with push & pull*'
        details:
          - 'Units can be reordered using `push` and `pull` classes.'
          - '![](grid-reorder.svg)'
          - |
            ```html
            <div class="grid">
              <div class="unit s-1 l-1-2 unit-push-l-1-2">Unit 1</div>
              <div class="unit s-1 l-1-2 unit-pull-l-1-2">Unit 2</div>
            </div>
            ```

  - title: 'Common problems'
    items:
      - name: '*Smushy text*'
        details:
          - 'The letters of the text look all smushed together — this is caused by text being inside `.grid` but not inside `.unit`.'
          - '![](smushy-text.svg)'
          - |
            ```html
            <div class="grid">
              <!-- Nothing can be outside the .unit -->
              <h2>This text would be smushy</h2>
              <div class="unit">…</div>
            </div>
            ```
      - name: '*Units not responding properly*'
        details:
          - 'Missing the wrapping `.grid` class.'
          - |
            ```html
            <!-- This element needs to always have the .grid class -->
            <main>
              <div class="unit">…</div>
              <div class="unit">…</div>
            </main>
            ```
          - 'Forgetting to close the `.grid` tag.'
          - |
            ```html
            <div class="grid">
              <div class="unit">…</div>
              <div class="unit">…</div>

            <!-- Because the above .grid isn’t closed, nothing will work properly -->
            <div class="grid">
              <div class="unit">…</div>
              <div class="unit">…</div>
            </div>
            ```
          - 'Having elements inside `.grid` but not inside `.unit`'
          - |
            ```html
            <div class="grid">
              <!-- Don’t have elements directly inside the grid that aren’t .unit tags -->
              <main>
                <div class="unit">…</div>
                <div class="unit">…</div>
              </main>
            </div>
            ```


---
