---
playlist: PLWjCJDeWfDdcu0Zh4Qe_8th4jr6FY5TnR
download: https://github.com/acgd-learn-the-web/tables-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/tables-code
cheatsheet: tables-cheat-sheet
---

HTML has the ability to make complex data tables—with a little extra care they can be completely accessible.

---

## Tabular data

Tables are great for large datasets, similar to how spreadsheets like in Excel or Numbers work.

### Rows & cells

Tables are composed of rows, that move vertically, stacking on top of each other. Each row is then broken down into cells, that move horizontally across the page.

Here’s an example of what the structure looks like:

<table>

  <thead>
    <tr>
      <th scope="col" rowspan="2">Name</th>
      <th scope="col" rowspan="2">Period</th>
      <th scope="col" rowspan="2">Discovery</th>
      <th class="size-heading" scope="col" colspan="2">Size</th>
    </tr>
    <tr>
      <th scope="col">Length</th>
      <th scope="col">Mass</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <th scope="row">Stegosaurus</th>
      <td>Late Jurassic</td>
      <td>1877</td>
      <td>9 m</td>
      <td>4.5 t</td>
    </tr>
    <tr>
      <th scope="row">Apatosaurus</th>
      <td>Jurassic Period</td>
      <td>1877</td>
      <td>23 m</td>
      <td>35 t</td>
    </tr>
    <tr>
      <th scope="row">Tyrannosaurus</th>
      <td>Late Cretaceous</td>
      <td>1905</td>
      <td>12.3 m</td>
      <td>6.8 t</td>
    </tr>
  </tbody>

  <tfoot>
    <tr>
      <th scope="row">Total</th>
      <td colspan="4">3 dinosaurs</td>
    </tr>
  </tfoot>

</table>

In HTML you can start a table with the `<table>` element. Each row is represented by the `<tr>` element. And each cell is represented by a `<td>`.

So, in HTML, a simplified version of the above table would look like this:

```html
<!-- <table> to surround everything -->
<table>
  <!-- <tr> to represent a row -->
  <tr>
    <!-- <td> to represent a cell or column -->
    <td>Stegosaurus</td>
    <td>Late Jurassic</td>
    <td>1877</td>
    <td>9 m</td>
    <td>4.5 t</td>
  </tr>
  <tr>
    ⋮
  </tr>
  ⋮
</table>
```

- `<table>` — wraps around all the information in the chart.
- `<tr>` — denotes a single row, no cell (`<td>`) can be outside of a row.
- `<td>` — represents the actual data, a cell, they must be inside a row.

---

## Table headings

For better accessibility, we should label the headings of a table, both vertically and horizontally, as headings using the `<th>` tag. The `<th>` is just a specialized version of the `<td>` with stronger semantics meaning “heading”.

In the sample table above that would be a cell like “Name” or “Stegosaurus”.

```html
<th>Name</th>
```

*or*

```html
<th>Stegosaurus</th>
```

But, for the most accessibility, we need to specify whether the heading labels a column, vertically, or labels a row, horizontally.

To label the direction, we use the `scope` attribute:

- `scope="col"` — labels a heading for vertical columns
- `scope="row"` — labels a heading for horizontal rows


```html
<th scope="col">Name</th>
<th scope="row">Stegosaurus</th>
```

---

## Merging cells

We can merge cells in columns and rows and a combination of both. In the table above we can see that “Name”, “Period”, & “Discovery” are all merged vertically and “Sizes” is merged horizontally.

- `colspan` — allows us to merge cells together accross columns horizontally
- `rowspan` — allows us to merge cells together across rows vertically

*The number of cells in each row and column should always add up to the same amount.*

```html
<th scope="col" rowspan="2">Name</th>
<th scope="col" colspan="2">Size</th>
```

---

## Headers, body & footers

When we have more than one row representing the headers or rows that represent totals for the table it’s a good idea to group them together using `<thead>`, `<tbody>` and `<tfoot>`.

```html
<table>
  <!-- <thead> to wrap around rows representing headers -->
  <thead>
    <tr>…</tr>
    <tr>…</tr>
    ⋮
  </thead>
  <!-- <tbody> to wrap around the main content of the table -->
  <tbody>
    <tr>…</tr>
    <tr>…</tr>
    ⋮
  </tbody>
  <!-- <tfoot> to wrap around rows representing footers, like totals, etc. -->
  <tfoot>
    <tr>…</tr>
    <tr>…</tr>
    ⋮
  </tfoot>
</table>
```

- `<thead>` — groups a bunch of rows together making them represent the “header” of the table.
- `<tbody>` — groups a bunch of rows together making them represent the “main contenț” of the table.
- `<tfoot>` — groups a bunch of rows together making them represent the “footer” or “totals” of the table.

*All these elements must have `<tr>` tags inside them—they are not a replacement for rows.*

The `<tfoot>` can actually be place above the `<tbody>` in the HTML and it will still be rendered at the bottom of the table.

---

## Styling tables

There are a few important CSS properties and ideas to know about when styling tables.

By default, the cells have spacing around them so borders are separated. Using CSS `border-collapse` we can eliminate the extra space.

```css
table {
  border-collapse: collapse;
}
```

Aligning the text within cells can be done simply with `vertical-align`.

```css
th {
  vertical-align: bottom; /* or middle, top */
}
```

**Beyond those specialized CSS properties, tables can be treated just like any other element. Borders, fonts, classes, etc.**

### Cols & colgroups

You can style columns in the table without having to put a class on each cell.

At the top of the table, add a `<col>` tag, with a class, and style that class. Styling the `<col>` tag has some limitations: many CSS properties won’t work, it’s really intended for `background-color` and a few others.

*The `<col>` tag is an empty tag—with absolutely no content. You can only add classes to it.*

With this HTML:

```html
<table>
  <!-- You need a `<col>` for each cell -->
  <col>
  <col>
  <col class="size">
  <col>
  <tr>
    <td>…</td>
    <td>…</td>
    <td>…</td>
    <td>…</td>
  </tr>
</table>
```

You could do this in CSS:

```css
.size {
  background-color: limegreen;
}
```

If you want to group the column styles together, you can use `<colgroup>`:

```html
<table>
  <colgroup>
    <col>
    <col>
  </colgroup>
  <col class="size">
  <col>
  <tr>
    <td>…</td>
    <td>…</td>
    <td>…</td>
    <td>…</td>
  </tr>
</table>
```

---

## Captioning a table

It’s usually a good idea to add a summary of the table’s contents—especially for accessibility reasons.

The summary is added using the `<caption>` element:

```html
<table>
  <caption>Information on three awesome dinosaurs.</caption>
  ⋮
</table>
```

If people are using a screen reader they can listen to the caption and then choose whether they want to venture into the table for more information or just skip over it.

---

## Elements inside cells

Inside the `<td>` and `<th>` elements you can put practically any HTML you want, including another table.

```html
<table>
  <tr>
    <td>
      <div>A div!</div>
      <ul>
        <li>A</li>
        <li>Super</li>
        <li>List</li>
      </ul>
    </td>
    <td>
      <p>A paragraph</p>
      <time datetime="2233-03-22">Time element</time>
    </td>
  </tr>
</table>
```

### Table in a table

Tables can be embedded inside of other tables, specifically inside another `<td>`.

```html
<table>
  <tr>
    <td>

      <table>
        <tr>
          <td>Table-ception</td>
        </tr>
      </table>

    </td>
  </tr>
</table>
```

---

## Video list

1. [Tables: rows and columns](https://www.youtube.com/watch?v=XG_RicH7TLY&list=PLWjCJDeWfDdcu0Zh4Qe_8th4jr6FY5TnR&index=1)
2. [Tables: headings](https://www.youtube.com/watch?v=6PZAfgb2ApU&list=PLWjCJDeWfDdcu0Zh4Qe_8th4jr6FY5TnR&index=2)
3. [Tables: merging cells with colspan and rowspan](https://www.youtube.com/watch?v=6TaHiaYzvgc&list=PLWjCJDeWfDdcu0Zh4Qe_8th4jr6FY5TnR&index=3)
4. [Tables: headers, body, footers](https://www.youtube.com/watch?v=e7R3ljHNG8M&list=PLWjCJDeWfDdcu0Zh4Qe_8th4jr6FY5TnR&index=4)
5. [Tables: styling](https://www.youtube.com/watch?v=I-UhJyQ7oR4&list=PLWjCJDeWfDdcu0Zh4Qe_8th4jr6FY5TnR&index=5)
6. [Tables: other elements in cells](https://www.youtube.com/watch?v=4w-XTc93r8c&list=PLWjCJDeWfDdcu0Zh4Qe_8th4jr6FY5TnR&index=6)

## Supplemental links

- [Table Generator](http://www.tablesgenerator.com/html_tables)
- [MDN: Tables](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
