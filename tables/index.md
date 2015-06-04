---
group: web-dev-2
playlist: PLWjCJDeWfDdcu0Zh4Qe_8th4jr6FY5TnR
download: https://github.com/acgd-learn-the-web/tables-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/tables-code
cheatsheet: tables-cheat-sheet
---

Making data tables in HTML that are completely accessible

---

## Rows & cells

Tables, like spreadsheets in Excel or Numbers, are made up of rows. Each row is then broken down into cells.

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

---

## Table headings

For the most accessibility, we should label the headings of a table, both vertically and horizontally, as headings using the `<th>` tag.

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
