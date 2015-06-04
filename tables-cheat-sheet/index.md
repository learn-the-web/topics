---
layout: cheatsheet
group: web-dev-2

groups:
  - title: 'Tags'
    items:
      - name: '`<table>`'
        details:
          - ''
      - name: '`<tr>`'
        details:
          - ''
      - name: '`<th>`'
        details:
          - ''
      - name: '`<td>`'
        details:
          - ''
      - name: '`<thead>`'
        details:
          - ''
      - name: '`<tbody>`'
        details:
          - ''
      - name: '`<tfoot>`'
        details:
          - ''
      - name: '`<caption>`'
        details:
          - ''
      - name: '`<col>`'
        details:
          - ''
      - name: '`<colgroup>`'
        details:
          - ''
      - name: '``'
        details:
          - ''

  - title: 'CSS snippets'
    items:
      - name: '*Remove border doubling*'
        details:
          - |
            ```css
            table {
              border-collapse: collapse;
            }
            ```
      - name: '*Zebra stripe rows*'
        details:
          - |
            ```css
            tr:nth-child(even) {
              background-color: #e2e2e2;
            }
            ```
      - name: '*Style columns*'
        details:
          - |
            ```html
              <table>
                <col class="thang">
                <colgroup class="things">
                  <col>
                  <col>
                </colgroup>
              ⋮
            ```

            ```css
              .thang {
                background-color: #e2e2e2;
              }

              .things {
                background-color: #ccc;
              }
            ```

---
