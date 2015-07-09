---
layout: cheatsheet
group: web-dev-1

groups:
  - title: 'Image formats'
    items:
      - name: 'SVG'
        details:
          - ''
          - ''
      - name: 'JPG'
        details:
          - ''
          - ''
      - name: 'PNG'
        details:
          - ''
          - ''
      - name: 'Favicons'
        details:
          - ''
          - ''
      - name: 'GIF'
        details:
          - ''
          - ''


  - title: 'HTML tags'
    items:
      - name: '`<img>`'
        details:
          - ''
          - ''
      - name: '`<figure>`'
        details:
          - ''
          - ''
      - name: '`<picture>`'
        details:
          - ''
          - ''
          - ''


  - title: 'CSS properties'
    items:
      - name: '`background-image`'
        details:
          - |
            ```css
            h1 {
              background-image: url("../images/grey-box.png");
            }

            h1 {
              background-image:
                url("../images/grey-box.png"),
                url("../images/green-box.png")
              ;
            }
            ```
      - name: 'gradients'
        details:
          - |
            ```css
            body {
              background-image: linear-gradient(to right, purple, darkpurple);
            }
            ```
      - name: 'flexible images'
        details:
          - |
            ```css
            .flex {
              display: block;
              width: 100%;
            }
            ```
      - name: 'image replacement'
        details:
          - |
            ```css
            .ir {
              overflow: hidden;
              text-indent: 100%;
              white-space: nowrap;
            }
            ```

---
