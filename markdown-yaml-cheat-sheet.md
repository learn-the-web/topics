---
layout: cheatsheet
title: "Markdown & YAML cheat sheet"
tags: "writing yaml markdown syntax cheat sheet"
desc: "A cheat sheet for understanding and writing in Markdown and YAML."

groups:
  - title: 'Markdown'
    items:
      - name: '*Paragraphs*'
        details:
          - 'Separate paragraphs with a blank line.'
          - |
            ```markdown
            This is a paragraph of text.

            And another paragraph of text.
            ```
      - name: '`#` — Headings'
        details:
          - 'Start each heading with one or more hashes, followed by a space.'
          - |
            ```markdown
            # Heading level 1
            ## Heading level 2
            ### Heading level 3
            ```
      - name: '`*` — Italic'
        details:
          - 'Wrap the words in single asterisks.'
          - |
            ```markdown
            Some of *these* words *are* italic.
            ```
      - name: '`**` — Bold'
        details:
          - 'Wrap the words in double asterisks.'
          - |
            ```markdown
            **Some** of these **words** are bold.
            ```
      - name: '`-` — Unordered list'
        details:
          - 'Start each line with a dash and a space.'
          - 'Indent before the dash for nested lists.'
          - |
            ```markdown
            - List item 1
            - List item 2
              - Sub list item 1
            ```
      - name: '`1.` — Ordered list'
        details:
          - 'Start each line with a number, period & space.'
          - 'Indent before the number for nested lists.'
          - |
            ```markdown
            1. List item one
            2. List item two
              1. Sub list item one
            ```
      - name: '`[]()` — Link'
        details:
          - '`[]` — link text inside square brackets.'
          - '`()` — link URL inside round brackets.'
          - |
            ```markdown
            [Dinosuars](https://en.wikipedia.org/wiki/Dinosaurs)

            The [New Horizons](http://pluto.jhuapl.edu/) space probe took photos of Pluto.
            ```
      - name: '`![]()` — Image'
        details:
          - 'Start with an exclamation point.'
          - '`[]` — alt text inside square brackets.'
          - '`()` — image URL inside round brackets.'
          - |
            ```markdown
            ![True colour composite of Pluto](true-colour-pluto.jpg)
            ```
      - name: '`---` — Horizontal rule'
        details:
          - 'Three consecutive dashes on a single line.'
          - |
            ```markdown
            ---
            ```
      - name: '<code>`</code> — Inline code'
        details:
          - 'Surround code inside other text with single backticks.'
          - |
            ```markdown
            The `<h1>` tag is the most important content on the page.
            ```
      - name: '<code>```</code> — Code block'
        details:
          - 'Start a line with three backticks to make a code block.'
          - 'End the code block with three more backticks on their own line.'
          - |
            <pre class="language-markdown"><code class="language-markdown">```
            body {
              font-size: 100%;
            }
            ```
            </code></pre>
          - 'Optionally specify the code language after the opening backticks.'
          - |
            <pre class="language-markdown"><code class="language-markdown">```css
            body {
              font-size: 100%;
            }
            ```
            </code></pre>
      - name: '`- [ ]` — Task list'
        details:
          - 'Non standard. Start a list and used square brackets with a space to denote a task.'
          - |
            ```markdown
            - [ ] Read sci-fi
            - [ ] Watch kaiju movie
            ```
          - 'Put an “x” between the square brackets to mark it as complete.'
          - |
            ```markdown
            - [ ] Read sci-fi
            - [x] Watch kaiju movie
            ```

  - title: 'YAML'
    note: 'Always indent with two spaces.'
    items:
      - name: '`term: value` — Objects'
        details:
          - 'Start with a term, no spaces, followed by a colon and a space.'
          - |
            ```yaml
            name: "Tyrannosaurus"
            period: "Late Cretaceous"
            ```
          - 'Indent to create nested objects.'
          - |
            ```yaml
            dimensions:
              width: "3 metres"
              height: "8 metres"
            ```
      - name: '`- value` — Arrays'
        details:
          - 'Start with a dash, and a space.'
          - |
            ```yaml
            - "Other dinosaurs"
            - "Meat"
            ```
          - 'Arrays inside objects:'
          - |
            ```yaml
            likes_to_eat:
              - "Other dinosaurs"
              - "Meat"
            ```
          - 'Objects inside arrays.'
          - |
            ```yaml
            - name: "T. rex"
              period: "Late Cretaceous Period"
            ```
      - name: '`"` — Escaping'
        details:
          - 'Surround text with quotes (double or single) to escape text.'
          - |
            ```yaml
            name_meaning: "tyrant & lizard"
            ```
          - In all the previous examples the quotes aren’t really necessary. But I find myself almost always adding them for clarity and to prevent myself from having to think about whether I need to escape them or not.
      - name: '`>` — Folded text block'
        details:
          - 'Start with a greater than, and indent the next lines.'
          - 'The text will be collapsed into a single line when parsed.'
          - |
            ```yaml
            desc: >
              Tyrannosaurus is a genus of coelurosaurian theropod dinosaur.
              The species Tyrannosaurus rex is one of the most well-represented of the large theropods.
            ```
      - name: '`|` — Wrapped text block'
        details:
          - 'Start with a vertical pipe, and indent the next lines.'
          - 'The text will keep its multiple lines when parsed.'
          - |
            ```yaml
            poem: |
              T. rex, T.rex
              How I love thee
            ```
      - name: '`---` — Front matter'
        details:
          - 'YAML can be used at the top of Markdown documents to add more structured data.'
          - 'Surround the YAML with two lines of consecutive dashes.'
          - |
            ```markdown
            ---
            name: "Venus"
            discoverer: "Galileo Galilei"
            ---

            *Venus* is the second planet from the Sun, orbiting it every 224.7 Earth days.
            ```

---
