---
layout: cheatsheet
title: "CSS grid cheat sheet"
tags: "css grid advanced layout columns flow template responsive cheat sheet"
desc: "A cheat sheet covering properties and use of the CSS grid system."

groups:
  - title: "Parents"
    notes: "Properties to apply to the parent grid container element."
    items:
      - name: "`display: grid`"
        details:
          - "Turn a parent, container element into a grid."
          - "Causes all children to flow into grid cells."
          - |
            ```css
            display: grid;
            ```
      - name: "`grid-template-columns`"
        details:
          - "Define how the columns are measured & how many there are."
          - |
            ```css
            /* 3 columns, equal size */
            grid-template-columns: 1fr 1fr 1fr;
            /* 3 columns, different sizes */
            grid-template-columns: 20rem 1fr;
            /* Create 12 equal-width columns */
            grid-template-columns: repeat(12, 1fr);
            ```
      - name: "`grid-template-rows`"
        details:
          - "Define how the rows are measured & how many there are."
          - |
            ```css
            /* 2 rows, equal size */
            grid-template-rows: 1fr 1fr;
            /* 2 rows, different sizes */
            grid-template-rows: auto 3rem;
            /* Create 6 equal-height rows */
            grid-template-rows: repeat(6, 1fr);
            ```
      - name: "`grid-template-areas`"
        details:
          - "Create a series of named areas within the parent to move elements into."
          - "Each grid row is contained by quotes."
          - "Each grid column is a word, separated by spaces, within the row quotes."
          - |
            ```css
            /* 3 columns, 3 rows
             * Areas spanning more than 1 column/row
             */
            grid-template-areas:
              "masthead masthead toolbar"
              "main     main     sidebar"
              "footer   footer   sidebar";
            ```
      - name: "`gap`, `column-gap`, `row-gap`"
        details:
          - "Create space like a margin between the columns/rows of the grid."
          - |
            ```css
            /* Between columns & rows */
            gap: 1rem;
            /* Between columns */
            column-gap: 1rem;
            /* Between rows */
            row-gap: 1rem;
            ```
      - name: "`justify-content` & `justify-items`"
        details:
          - "Align the elements horizontally within the grid."
          - "`content` moves all the elements together as a group."
          - "`items` moves each element individually within their area."
          - |
            ```css
            justify-content: center;
            justify-items: end;
            ```
      - name: "`align-content` & `align-items`"
        details:
          - "Align the elements vertically within the grid."
          - "`content` moves all the elements together as a group."
          - "`items` moves each element individually within their area."
          - |
            ```css
            align-content: start;
            align-items: center;
            ```
      - name: "`place-content` & `place-items`"
        details:
          - "Apply both `justify` and `align` at the same time."
          - |
            ```css
            place-content: start;
            place-items: end;
            ```
      - name: "`grid-auto-columns` & `grid-auto-rows`"
        details:
          - "Define the size of automatically generated intrinsic rows & columns."
          - |
            ```css
            grid-auto-columns: 1fr;
            grid-auto-rows: 10rem;
            ```
      - name: "`grid-auto-flow: dense`"
        details:
          - "Attempt to tightly pack grid cells, even moving cells earlier in the order."
          - |
            ```css
            grid-auto-flow: dense;
            ```

  - title: "Children"
    notes: "These properties are to be applied to the children of the grid parent container."
    items:
      - name: "`grid-column`"
        details:
          - "Choose which column the element starts & finishes at."
          - |
            ```css
            /* Start at column line 2 */
            grid-column: 2;
            /* Start at line 2, go to line 6 */
            grid-column: 2 / 6;
            /* Start at line 2, go to last line */
            grid-column: 2 / -1;
            /* Start at line 2, span horizontally 3 rows */
            grid-column: 2 / span 3;
            ```
      - name: "`grid-row`"
        details:
          - "Choose which row the element starts & finishes at."
          - |
            ```css
            /* Start at row line 2 */
            grid-row: 2;
            /* Start at line 2, go to line 6 */
            grid-row: 2 / 6;
            /* Start at line 2, go to last line */
            grid-row: 2 / -1;
            /* Start at line 2, span vertically 3 rows */
            grid-row: 2 / span 3;
            ```
      - name: "`grid-area`"
        details:
          - "Assign the element to a specific area in the grid."
          - |
            ```css
            grid-area: sidebar;
            ```
      - name: "`justify-self`"
        details:
          - "Move the element itself horizontally within its defined area."
          - |
            ```css
            justify-self: center;
            ```
      - name: "`align-self`"
        details:
          - "Move the element itself vertically within its defined area."
          - |
            ```css
            align-self: center;
            ```
      - name: "`place-self`"
        details:
          - "Apply both `justify-self` & `align-self` at the same time."
          - |
            ```css
            place-self: center;
            ```

  - title: "Getting fancy"
    items:
      - name: "*Automatic responsive columns*"
        details:
          - |
            ```css
            grid-template-columns: repeat(auto-fit, minmax(min(15rem, 100%), 1fr));
            ```
          - "Fit as many elements across a row, creating new rows as needed, with an ideal size of `15rem`"
          - "If you use this, only change `15rem`"
      - name: "`display: contents`"
        details:
          - "Use on a parent element to get its children onto the grid."
          - "Be careful with accessibility—some browsers don’t fully support it."
          - "[Subgrid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Subgrid) will eventually be a better option."

---
