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
            <link href="/favicon.ico" rel="shortcut icon">
            <meta name="application-name" content="Your Site Name">
            <link rel="apple-touch-icon-precomposed" href="/favicon-152.png">
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

  - title: 'CSS code'
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
            .img-flex {
              display: block;
              width: 100%;
            }
            ```
      - name: '*Image replacement*'
        details:
          - |
            ```css
            .visually-hidden {
              height: 1px;
              margin: -1px;
              overflow: hidden;
              padding: 0;
              position: absolute;
              width: 1px;
              border: 0;
              clip: rect(0 0 0 0);
              clip-path: inset(50%);
            }
            ```

---
