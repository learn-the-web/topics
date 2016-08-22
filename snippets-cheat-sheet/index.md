---
layout: cheatsheet

groups:
  - title: 'HTML'
    items:
      - name: '`html5`'
        details:
          - 'The HTML boilerplate code.'
          - |
            ```html
            <!DOCTYPE html>
            <html lang="en-ca">
            <head>
              <meta charset="utf-8">
              <title></title>
            </head>
            <body>
            </body>
            </html>
            ```
      - name: '`css`'
        details:
          - 'Creates a new CSS link tag.'
          - |
            ```html
            <link href=".css" rel="stylesheet">
            ```

      - name: '`viewport`'
        details:
          - 'Adds the responsive viewport tags.'
          - |
            ```html
            <meta name="viewport" content="width=device-width,initial-scale=1">
            ```

  - title: 'CSS'
    items:
      - name: '`cssviewport`'
        details:
          - 'Outputs the CSS viewport declarations.'
          - |
            ```css
            @viewport { width: device-width; scale: 1; }
            ```
      - name: '`borderbox`'
        details:
          - 'Outputs the CSS border box declarations for changing the layout math.'
          - |
            ```css
            html {
              box-sizing: border-box;
            }

            *, *::before, *::after {
              box-sizing: inherit;
            }
            ```
      - name: '`textsize`'
        details:
          - 'Outputs the text-size-adjust declarations to prevent mobile browsers from changing the font-size.'
          - |
            ```css
            text-size-adjust: 100%;
            ```
      - name: '`mq`'
        details:
          - 'Outputs a new media query, placing the cursor in the `min-width` location.'
          - |
            ```css
            @media only screen and (min-width: 25em) {

            }
            ```
---
