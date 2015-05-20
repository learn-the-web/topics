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
            <!-- First two tags optional, for older browsers -->
            <meta name="handheldfriendly" content="true">
            <meta name="mobileoptimized" content="240">
            <!-- Required -->
            <meta name="viewport" content="width=device-width,initial-scale=1">
            ```

---
