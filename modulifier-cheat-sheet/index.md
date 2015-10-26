---
layout: cheatsheet
group: web-dev-2

groups:
  - title: 'Responsive setup'
    items:
      - name: '*CSS viewport* & *text size*'
        details:
          - 'Will includes all the `@viewport` code.'
          - 'Will set `text-size-adjust` to prevent browsers from zooming text.'
      - name: '*Border box*'
        details:
          - 'Will add all the `border-box` code to change the layout math.'
      - name: '*Body margin*'
        details:
          - 'Will remove the default `margin` from `<body>` because it is almost never used.'
      - name: '*New HTML elements*'
        details:
          - 'Will set default styles for new HTML elements for better browser support.'

  - title: 'Images'
    items:
      - name: '*Remove border*'
        details:
          - 'Will remove the border from all images by default for better browser support.'
      - name: '`.img-flex`'
        details:
          - 'Creates the responsive `.img-flex` class that will make images `100%` the width of their container.'
      - name: '*SVG helpers*'
        details:
          - 'Will fix a browser bug related to embedded SVG.'
          - 'Add the ability for embedded SVG to inherit `fill` and `stroke` from the CSS `color` property.'
      - name: '`.image-replacement`, `.ir`'
        details:
          - 'Adds a class, and a shorter version, that will hide all the text inside an element and allow only the `background-image` to show.'

  - title: 'List group'
    note: 'These classes are brute force and not responsive, if you use list-group-inline, the list will always be inline.'
    items:
      - name: '`.list-group`'
        details:
          - 'Add a `.list-group` class that will remove bullets and padding from lists, so semantically the can be lists but no visually.'
      - name: '`.list-group--inline`'
        details:
          - 'Add a `.list-group--inline` class that will force the `<li>` tags onto the same line.'
      - name: '*List group example*'
        details:
          - |
            ```html
            <ul class="list-group list-group--inline">
              <li><a href="#">Dinosaurs</a></li>
              <li><a href="#">Plant eaters</a></li>
              <li><a href="#">Meat eaters</a></li>
            </ul>
            ```

  - title: 'Embed containers'
    items:
      - name: '`.embed`'
        details:
          - 'The wrapper class for making responsive embedded resources like images and videos.'
      - name: '`.embed__item`'
        details:
          - 'The class to be added directly to the embedded image or video.'
      - name: '*Embed container example*'
        details:
          - |
            ```html
            <figure>
              <div class="embed embed--4by3">
                <img class="embed__item" src="dinos.jpg" alt="">
              </div>
              <figcaption>Dinosaurs frolicking in the barren landscape</figcaption>
            </figure>

            <div class="embed embed--16by9">
              <video class="embed__item" src="dinos-frolicking.mp4" controls></video>
            </div>
            ```
      - name: '`.embed--1by1`'
        details:
          - 'Square.'
      - name: '`.embed--4by3`'
        details:
          - 'Traditional TV/computer screens.'
      - name: '`.embed--iso216`'
        details:
          - 'A-standard paper sizes.'
      - name: '`.embed--3by2`'
        details:
          - 'Classic 35 mm film.'
      - name: '`.embed--golden`'
        details:
          - 'The Golden Ratio.'
      - name: '`.embed--16by9`'
        details:
          - 'HD TV.'
      - name: '`.embed--185by100`'
        details:
          - 'Common widescreen cinema.'
      - name: '`.embed--24by10`'
        details:
          - 'Widescreen cinema: 2.4:1.'
      - name: '`.embed--3by1`'
        details:
          - 'Panorama photos.'
      - name: '`.embed--4by1`'
        details:
          - 'Polyvision.'
      - name: '*Making a new ratio*'
        details:
          - 'Take the height, divide by the width and multiply by 100 — `h ÷ w × 100`'
          - 'An image with the dimensions: 950 × 1427: `1427 ÷ 950 × 100 = 105%`'

  - title: 'Media objects'
    items:
      - name: '`.media`'
        details:
          - 'A wrapper class to surround image & text groups, especially if the images is to be beside the text.'
      - name: '`.media__img`'
        details:
          - 'A class for adding to the image, or surrounding `<div>`, within the media object.'
      - name: '`.media__body`'
        details:
          - 'A class to add to the text, or surrounding `<div>`, within the media object.'
      - name: '`.media__img--reversed`'
        details:
          - 'Instead of floating the image left it will `float: right`'
      - name: '`.media__img--stacked`'
        details:
          - 'Will disable floating and have the image above the text instead.'
      - name: '*Media object example*'
        details:
          - |
            ```html
            <div class="media">
              <div class="media__img media__img--reversed">
                <img src="images/parsnips.jpg" alt="">
              </div>
              <div class="media__body">
                <h2 class="media-title">Parsnips</h2>
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
              </div>
            </div>
            ```

  - title: 'Icons'
    items:
      - name: '`.icon`'
        details:
          - 'To be added to a tag, usually `<i>` to mark it as being an icon.'
          - 'Usually you add another class to define the `background-image`'
          - 'Will also add some CSS to support embedded SVG icons with the `<svg>` and `<use>` tags.'
      - name: '`.icon-label`'
        details:
          - 'Can be added to the neighbouring text to allow the icon and the text to align.'
      - name: '`.icon-link`'
        details:
          - 'Can be added to the surrounding `<a>` tag to remove the `text-decoration`'
      - name: '`.i--16`'
        details:
          - 'A 16 × 16 pixel sized icon.'
      - name: '`.i--18`'
        details:
          - 'A 18 × 18 pixel sized icon.'
      - name: '`.i--24`'
        details:
          - 'A 24 × 24 pixel sized icon.'
      - name: '`.i--32`'
        details:
          - 'A 32 × 32 pixel sized icon.'
      - name: '`.i--48`'
        details:
          - 'A 48 × 48 pixel sized icon.'
      - name: '*Icons example*'
        details:
          - |
            ```html
            <a class="icon-link" href="#">
              <i class="icon i--32 i--github"></i>
              <span class="icon-label">GitHub</span>
            </a>
            ```

            ```css
            .i--github {
              background-image: url("../img/github.svg");
            }
            ```

  - title: 'Hidden'
    items:
      - name: ''
        details:
          - ''

  - title: 'Positioning'
    items:
      - name: ''
        details:
          - ''

  - title: 'Basic buttons'
    items:
      - name: ''
        details:
          - ''

  - title: 'Forms'
    items:
      - name: ''
        details:
          - ''

  - title: 'Accessibility'
    items:
      - name: ''
        details:
          - ''

  - title: 'Print styles'
    items:
      - name: ''
        details:
          - ''

---
