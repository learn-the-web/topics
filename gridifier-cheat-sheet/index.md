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

---
