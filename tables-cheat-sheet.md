---
layout: cheatsheet
title: "Tables cheat sheet"
tags: "table chart cells data cheat sheet"
desc: "A cheat sheet explaining the tags and elements for creating HTML tables."

groups:
  - title: 'Tags'
    items:
      - name: '`<table>`'
        details:
          - 'The element that surrounds all other table elements.'
          - '*No other table element can be outside the `<table>`*'
      - name: '`<tr>`'
        details:
          - 'Defines a row of cells in the table.'
      - name: '`<th scope="…">`'
        details:
          - 'Defines a heading cell to label a row or column.'
          - '`scope="row"` — for row labels.'
          - '`scope="col"` — for column labels.'
      - name: '`<td>`'
        details:
          - 'Defines a single piece of data in the table—a cell.'
          - 'Can have many other HTML elements inside, including other tables.'
          - '`rowspan="…"` — allows merging of cells vertically.'
          - '`colspan="…"` — allows merging of cells horizontally.'
      - name: '`<thead>`'
        details:
          - 'To group the table rows that define the headers.'
          - 'Must have at least one `<tr>` inside.'
      - name: '`<tbody>`'
        details:
          - 'To group the table rows that account for the main data.'
      - name: '`<tfoot>`'
        details:
          - 'To group the table rows that define the footer, like totals.'
          - 'Must have at least one `<tr>` inside.'
      - name: '`<caption>`'
        details:
          - 'To add a visible caption that describes the purpose of the table.'
          - '*Really good for accessibility.*'
      - name: '`<col>`'
        details:
          - 'Non-visible element that defines a column for styling.'
      - name: '`<colgroup>`'
        details:
          - 'Non-visible element that defines a group of columns for accessibility and styling.'

  - title: 'Examples'
    items:
      - name: '*Headers & footers*'
        details:
          - |
            ```html
              <table>
                <thead>
                  <tr>
                    <th scope="col">Name</th>
                    <th scope="col">Price</th>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <td>Chocolate</td>
                    <td>$4.99</td>
                  </tr>
                  <tr>
                    <td>Candy</td>
                    <td>$3.99</td>
                  </tr>
                </tbody>
                <tfoot>
                  <tr>
                    <th scope="total">Total</th>
                    <td>$8.89</td>
                  </tr>
                </tfoot>
              </table>
            ```
      - name: '*Merging cells*'
        details:
          - |
            ```html
              <table>
                <tr>
                  <td>&nbsp;</td>
                  <th scope="col">Name</th>
                  <th scope="col">Discovery</th>
                </tr>
                <tr>
                  <th rowspan="2" scope="row">Plant eaters</th>
                  <td>Apatosaurus</td>
                  <td>1877</td>
                </tr>
                <tr>
                  <td>Stegosaurus</td>
                  <td>1877</td>
                </tr>
                <tr>
                  <th scope="row">Meat eaters</th>
                  <td>Tyrannosaurus</td>
                  <td>1905</td>
                </tr>
              </table>
            ```
      - name: '*Captioned table*'
        details:
          - |
            ```html
              <table>
                <caption>Important dinosaur discoveries from history.</caption>
                <tr>
                  <th scope="col">Name</th>
                  <th scope="col">Discovery</th>
                </tr>
                <tr>
                  <td>Apatosaurus</td>
                  <td>1877</td>
                </tr>
                <tr>
                  <td>Stegosaurus</td>
                  <td>1877</td>
                </tr>
              </table>
            ```

  - title: 'CSS snippets'
    items:
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

---
