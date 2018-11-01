---
layout: cheatsheet
title: "Images cheat sheet"
tags: "images png jpg svg gif web compression cheat sheet"
desc: "A cheat sheet covering the basics of web image formats, compression, and use."

groups:
  - title: 'Image formats'
    items:
      - name: '**SVG**'
        details:
          - '*Vector graphic:* good for graphics with few colours, animations; can manipulate with code.'
          - 'Very scalable and retina ready.'
          - '---'
          - '*Export settings:* Styling: Presentation attributes, Font: Convert to outline, Images: Link, Object IDs: Layer names, Decimal: 1, Check minify, Uncheck responsive.'
      - name: '**JPG**'
        details:
          - '*Raster graphic:* good for photos and complex imagery.'
          - 'For retina: determine max dimensions on website, double the original graphic size, compress to around 20%.'
          - 'Link inside an SVG to get masks & transparency.'
          - '---'
          - '*Export settings:* Compression: ~65% (~20% for double-sized retina), Progressive, Uncheck embed color profile, Internet Standard RGB, Metadata: None.'
      - name: '**PNG**'
        details:
          - '*Raster graphic:* good for graphics with few colours.'
          - 'PNG-24 has millions of colours & 256 levels of transparency.'
          - 'PNG-8 has 256 colours—Photoshop’s implementation is incorrect, use [ImageAlpha](http://pngmini.com/).'
          - 'Not really retina capable: use SVG instead.'
          - '---'
          - '*Export settings:* Interlaced, Uncheck embed color profile, Internet Standard RGB, Metadata: None.'
      - name: '**Favicons**'
        details:
          - 'Small icons used in different places on browsers.'
          - 'Use a tool like [Icon Slate](http://xiconeditor.com/) or [X Icon Editor](http://xiconeditor.com/) to convert the PNGs into an `.ico` file.'
          - '*ICO sizes:* 16×16, 32×32 & 48×48.'
          - '*PNG sizes:* 152×152, 144×144 (transparent).'
      - name: '**GIF**'
        details:
          - 'Limited to 256 colours, can be animated.'
          - '*Try to avoid using.*'
          - 'Use only for animations but using video is still preferred.'


  - title: 'HTML tags'
    items:
      - name: '`<img src="…" alt="">`'
        details:
          - 'For inserting content-related images.'
          - 'Use the `alt="…"` to describe the image, blank alt for decorative images.'
          - 'If a formatted description is needed use `aria-details="…"`'
          - 'Use the `srcset="…"` & `sizes=""` attributes for responsiveness.'
      - name: '`<figure>`'
        details:
          - 'For images that need captions.'
          - 'Use the `<img>` and `<figcaption>` tags inside.'
          - '*Use only `<figure>` with a caption, or if the image can be removed from its location and still make sense, e.g. “Refer to Figure 1”.*'
      - name: '`<picture>`'
        details:
          - 'Used for art direction of responsive images: different crops on different screens, etc.'
          - 'Needs the `<source>` and `<img>` tags inside.'

  - title: 'HTML examples'
    items:
      - name: '*Image tag*'
        details:
          - |
            ```html
            <img src="pluto.jpg" alt="Photo of Pluto">
            ```
      - name: '*Figure*'
        details:
          - |
            ```html
            <figure>
              <img src="pluto.jpg" alt="">
              <figcaption>Photo of Pluto taken with the Hubble Telescope</figcaption>
            </figure>
            ```
      - name: '*Favicons*'
        details:
          - |
            ```html
            <!-- .ico should have 16, 32, 48 px sizes -->
            <link href="/favicon.ico" rel="shortcut icon">
            <link href="/favicon-196.png" rel="icon" type="image/png">

            <!-- Very optional -->
            <meta name="application-name" content="Your Site Name">
            <link rel="apple-touch-icon-precomposed" href="/favicon-196.png">
            <meta name="msapplication-TileImage" content="/favicon-144.png">
            <meta name="msapplication-TileColor" content="#ef0303">
            ```
      - name: '*Responsive & retina image tag*'
        details:
          - |
            ```html
            <img
              src="small.jpg"
              srcset="larage.jpg 2000w, medium.jpg 1000w, small.jpg 320w"
              sizes="(min-width: 38em) 50vw, 100vw"
              alt="A giant squid swimming deep in the sea"
            >
            ```
      - name: '*Picture*'
        details:
          - |
            ```html
            <picture>
              <source media="(min-width: 60em)" srcset="high.jpg">
              <source media="(min-width: 35em)" srcset="medium.jpg">
              <img src="small.jpg" alt="A giant squid swimming deep in the sea">
            </picture>
            ```
      - name: '*Retina picture*'
        details:
          - |
            ```html
            <picture>
              <source media="(min-width: 60em)" srcset="large-2x.jpg 2x, large.jpg 1x">
              <source media="(min-width: 35em)" srcset="medium-2x.jpg 2x, medium.jpg 1x">
              <img src="small.jpg" srcset="small-2x.jpg 2x, small.jpg 1x" alt="A giant squid swimming deep in the sea">
            </picture>
            ```

  - title: 'CSS background images'
    items:
      - name: '`background-image`'
        details:
          - 'Link an image and display in behind the text of an element.'
          - 'The path is relative to the CSS file, and usually starts with `../`'
          - |
            ```css
            background-image: url("../images/icon.png");
            ```
          - '**Separate multiple images with a comma (`,`).**'
          - |
            ```css
            background-image: url("../images/star.svg"), url("../images/hex.svg");
            ```
          - 'The first image is the one that will be on top, each image further along will be a lower layer.'
      - name: '`background-position`'
        details:
          - 'Move a background image around inside the element.'
          - 'Accepts `px`, `%` or keywords.'
          - '**Horizontal position must come first, vertical position second.**'
          - |
            ```css
            /* 10px in from the left, 25px down from the top */
            background-position: 10px 25px;

            /* Stuck to right side, in the vertical center */
            background-position: right center;

            /* Move up from the bottom with calc(): 25px up from the bottom */
            background-position: center calc(100% - 25px);
            ```
          - '*Horizontal keywords:* `left`, `center`, `right`'
          - '*Vertical keywords:* `top`, `center`, `bottom`'
      - name: '`background-repeat`'
        details:
          - 'Control how the background image patterns.'
          - '`no-repeat`, `repeat`, `repeat-x`, `repeat-y`, `space`, `round`'
          - |
            ```css
            /* Don’t repeat in either direction */
            background-repeat: no-repeat;
            /* Repeat only horizontally */
            background-repeat: repeat-x;
            /* Repeat only vertically */
            background-repeat: repeat-y;
            /* Get browser to determine how to repeat the image well */
            background-repeat: space;
            background-repeat: round;
            ```
          - '`background-repeat: space` — do not crop the image, but put space around the repeated ones.'
          - '`background-repeat: round` — scale the image up so there’s always a full version, no cropping.'
          - '*Or, use horizontal & vertical values like* `background-position`'
          - |
            ```css
            background-repeat: no-repeat repeat;
            ```
      - name: '`background-size`'
        details:
          - 'Scale the background image inside its element.'
          - 'Accepts `px`, `%`, keywords, or `auto`.'
          - '**Width always must come first, height second.**'
          - |
            ```css
            /* Scale to 256 pixels wide & tall */
            background-size: 256px 256px;

            /* Scale to 128 pixels wide, automatically determine the correct height */
            background-size: 128px auto;

            /* Scale to 50% the width of the element, auto height */
            background-size: 50% auto;

            /* Keywords for automatically scaling the image */
            background-size: cover;
            background-size: contain;
            ```
          - '`background-size: cover` — fill the whole element, cropping the image.'
          - '`background-size: contain` — make sure the whole image is visible, unused areas will show the `background-color`'
      - name: '`background-attachment`'
        details:
          - 'Prevent the image from moving when the browser is scrolled, a parallax-like effect.'
          - |
            ```css
            background-attachment: fixed;
            ```
          - 'The default value, that all images are, is `scroll`'
      - name: '*Shorthand syntax*'
        details:
          - 'Combine everything into a single line instead of separate `background-*` properties.'
          - '`background` should follow this order:'
          - '• `background-image`'
          - '• `background-position` / `background-size`'
          - '• `background-repeat`'
          - '• `background-color`'
          - |
            ```css
            /* This can be written on a single line too */
            background:
              url("../images/star.svg")
              left top / 32px auto
              round
              indigo
              ;
            ```
          - '*Or with multiple background images:*'
          - |
            ```css
            background: linear-gradient(to bottom, rgba(255, 255, 255, 0), rgba(255, 255, 255, .6)), url("../images/star.svg") left top / 32px auto round indigo;
            ```

  - title: 'CSS gradients'
    notes: 'Always provide a `background-color` when using gradients.'
    items:
      - name: '*Gradients*'
        details:
          - 'The browser will generate a background-image gradient for you.'
          - |
            ```css
            background-image: linear-gradient(to right, purple, indigo);
            ```
          - 'Angle the gradient by adjusting the first value:'
          - |
            ```css
            background-image: linear-gradient(33deg, purple, indigo);
            ```
          - 'Also radial gradients, with the keywords `circle` or `ellipse` followed by a position'
          - |
            ```css
            background-image: radial-gradient(circle at center, purple, indigo);
            ```
      - name: '*Gradients with stops*'
        details:
          - 'Control the gradient colour positions using colour-stops.'
          - 'Each colour can have it’s own stop value.'
          - |
            ```css
            /* Two purples separated by a sharp black line */
            background-image: linear-gradient(33deg, purple 0%, purple 49%, black 49%, black 50%, indigo 50%);
            ```
          - 'Also works for `radial-gradient()`'
      - name: '*Repeated gradients*'
        details:
          - 'Create a gradient that repeats itself multiple times within an element.'
          - |
            ```css
            /* Black/yellow warning stripes */
            background-image: repeating-linear-gradient(45deg, yellow, yellow 10%, black 10%, black 20%);
            ```
          - 'Also `repeating-radial-gradient()`'

  - title: 'Border images'
    notes: 'Use an image around the edges of the element instead of a plain border. [Border-image generator](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Background_and_Borders/Border-image_generator).'
    items:
      - name: '`border-image-source`'
        details:
          - 'The path to the image file.'
          - |
            ```css
            border-image-source: url("../images/border.svg");
            ```
      - name: '`border-image-slice`'
        details:
          - 'How to slice the image into 9 pieces—called 9-slicing.'
          - 'Same order as `margin`, `padding`: top, right, bottom, left.'
          - |
            ```css
            /* 36px in from every edge */
            border-image-slice: 36px;
            /* 36px in from top/bottom; 24px in from left/right */
            border-image-slice: 36px 24px;
            /* 36px from top, 24px from right, 12px from bottom, 17px from left */
            border-image-slice: 36px 24px 12px 17px;
            ```
      - name: '`border-image-repeat`'
        details:
          - 'Tells the browser how to handle the long central edge regions.'
          - '`repeat`, `stretch`, `round`, `space`'
          - 'Same as `background-repeat`: horizontal first, vertical second.'
          - |
            ```css
            /* Same in both directions */
            border-image-repeat: repeat;
            /* Round horizontally, space vertically */
            border-image-repeat: round space;
            ```
          - '`border-image-repeat: space` — do not crop the slice, but put space around the repeated ones.'
          - '`border-image-repeat: round` — scale the slice up so there’s always a full version, no cropping.'
      - name: '`border-image-width`'
        details:
          - 'The border image width will automatically scale to the width of the `border`'
          - 'This can overwrite that value to scale the image inwards from the box.'
          - 'Follows the same scheme as `margin`, `padding`'
          - |
            ```css
            /* 36px wide in every direction */
            border-image-width: 36px;
            /* 36px wide on top/bottom; 24px wide on left/right */
            border-image-width: 36px 24px;
            /* 36px wide top, 24px wide right, 12px wide bottom, 17px wide left */
            border-image-width: 36px 24px 12px 17px;
            ```
      - name: '`border-image-outset`'
        details:
          - 'How far to expand the border image outside the edge of the box dimensions.'
          - 'Follows the same scheme as `border-image-width`'
          - |
            ```css
            border-image-outset: 12px 16px;
            ```
      - name: '*Shorthand*'
        details:
          - 'Combine everything into a single line instead of separate `border-image-*` properties.'
          - '`border-image` should follow this order:'
          - '• `border-image-source`'
          - '• `border-image-slice`'
          - '• `border-image-width`'
          - '• `border-image-outset`'
          - '• `border-image-repeat`'
          - |
            ```css
            border-image: url("../images/border.svg") 36px repeat;
            ```
      - name: '*Image slicing example*'
        details:
          - 'How a border image is sliced.'
          - '![An example of a 9-sliced image](border-image.svg)'
      - name: '*Example CSS*'
        details:
          - 'Using the image on the example image…'
          - |
            ```css
            .box {
              border-image: url("../images/border.svg") 36px repeat;
            }

            /* Or longhand… */
            .box {
              border-image-source: url("../images/border.svg");
              border-image-slice: 36px;
              border-image-repeat: repeat;
            }
            ```
      - name: '*Gradient border image*'
        details:
          - 'Because border-images are just images, we can use gradients!'
          - |
            ```css
            .box {
              border: 8px solid indigo;
              border-image-source: linear-gradient(to bottom, blue, indigo);
              border-image-slice: 1;
            }
            ```

  - title: 'Common CSS code snippets'
    items:
      - name: '*Flexible images*'
        details:
          - |
            ```css
            .img-flex {
              display: block;
              width: 100%;
            }
            ```
      - name: '*Image replacement*'
        details:
          - |
            ```css
            .image-replacement {
              overflow: hidden;
              direction: ltr;
              text-align: left;
              text-indent: 100%;
              white-space: nowrap;
            }
            ```
      - name: '*Button gradient*'
        details:
          - |
            ```css
            .btn {
              display: inline-block;
              background-color: purple;
              background-image: linear-gradient(to bottom, purple, indigo);
              border-radius: 6px;
            }
            ```

---
