---
layout: cheatsheet

groups:
  - title: 'Image formats'
    items:
      - name: '**SVG**'
        details:
          - '*Vector graphic:* good for graphics with few colours, animations; can manipulate with code.'
          - 'Very scalable and retina ready.'
          - '---'
          - '*Export settings:* SVG 1.1, Convert to outline, Link, Style elements, Decimal places: 1, Uncheck responsive.'
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
          - 'If a formatted description is needed use `aria-describedat="…"`'
          - 'Use the `srcset="…"` attribute for responsiveness.'
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

            <img
              src="low-res.jpg"
              srcset="med-res.jpg 1000w, high-res.jpg 2000w"
              alt="A giant squid swimming deep in the sea"
            >
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
      - name: '*Picture*'
        details:
          - |
            ```html
            <picture>
              <source media="(min-width: 35em)" src="medium-res.jpg">
              <source media="(min-width: 60em)" src="high-res.jpg">
              <img src="low-res.jpg" alt="A giant squid swimming deep in the sea">
            </picture>
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
