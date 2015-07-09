---
layout: cheatsheet
group: web-dev-1

groups:
  - title: 'Image formats'
    items:
      - name: '*SVG*'
        details:
          - ''
          - ''
      - name: '*JPG*'
        details:
          - ''
          - ''
      - name: '*PNG*'
        details:
          - ''
          - ''
      - name: '*Favicons*'
        details:
          - ''
          - ''
      - name: '*GIF*'
        details:
          - ''
          - ''


  - title: 'HTML tags'
    items:
      - name: '`<img src="…" alt="">`'
        details:
          - 'For inserting content-related images.'
          - 'Use the `alt="…"` to describe the image, blank alt for decorative images.'
          - 'If a formatted description is needed use `aria-describedat="…"`'
          - 'Use the `srcset="…"` attribute for responsiveness.'
      - name: '`<figure>`'
        details:
          - 'For images that need captions.'
          - 'Use the `<img>` and `<figcaption>` tags inside.'
          - '*Don’t `<figure>` without a caption, or if the image can be removed from its location and still make sense, e.g. “Refer to Figure 1”.*'
      - name: '`<picture>`'
        details:
          - 'Used for art direction of responsive images: different crops on different screens, etc.'
          - 'Needs the `<source>` and `<img>` tags inside.'


  - title: 'CSS examples'
    items:
      - name: '*Background images*'
        details:
          - |
            ```css
            h1 {
              background-image: url("../images/icon.png");
            }
            ```
      - name: '*Gradients*'
        details:
          - |
            ```css
            body {
              background-image: linear-gradient(to right, purple, darkpurple);
            }
            ```
      - name: '*Flexible images*'
        details:
          - |
            ```css
            .flex {
              display: block;
              width: 100%;
            }
            ```
      - name: '*Image replacement*'
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
