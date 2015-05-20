---
layout: cheatsheet
group: setup

groups:
  - title: 'HTML'
    items:
      - name: '`html5`'
        details:
          - 'The HTML boilerplate code.'
          - |
            ```
            <!DOCTYPE html>
            <html lang="en-ca">
            <head>
              <meta charset="utf-8">
              <title></title>
            ⋮
            ```
      - name: '`css`'
        details:
          - 'Creates a new CSS link tag.'
          - |
            ```
            <link href="….css" rel="stylesheet">
            ```

      - name: '`viewport`'
        details:
          - 'Adds the responsive viewport tags.'
          - |
            ```
            <meta name="viewport" content="width=device-width,initial-scale=1">
            ```

  - title: 'CSS'
    items:
      - name: '`cssviewport`'
        details:
          - 'Outputs the CSS viewport declarations.'
          - |
            ```
            ⋮
            @viewport { width: device-width; scale: 1; }
            ```
      - name: '`borderbox`'
        details:
          - 'Outputs the CSS border box declarations for changing the layout math.'
          - |
            ```
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
            ```
            ⋮
            text-size-adjust: 100%;
            ```

---
