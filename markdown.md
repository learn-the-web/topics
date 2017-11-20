---
title: "Markdown"
tags: "markdown processor html headings daring fireball john gruber commonmark"
desc: "Understanding the Markdown markup language that’s used in many locations including GitHub."
playlist: PLWjCJDeWfDdeCy2wlIbAVfY4dLJx58ghX
download: https://github.com/acgd-learn-the-web/markdown-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/markdown-code
cheatsheet: markdown-yaml-cheat-sheet
extra_practice:
  week:
    title: "Web Dev 4, Week 04"
    url: "/courses/web-dev-4/week-04/"
  slides:
    - title: "Markdown & YAML"
      url: "/courses/web-dev-4/markdown-yaml/"
  activities:
    - title: "Markdown Manipulator"
      url: "markdown-manipulator"
  exercises:
    - title: "Pattern library README"
      url: "/courses/web-dev-4/pattern-library-readme/"
    - title: "Writing a README"
      url: "/courses/web-dev-5/writing-a-readme/"
---

Markdown is a lightweight syntax of markup for plain text documents. It allows us to add semantics and style to our documents without overpowering them with code and angle brackets.

Markdown can easily be converted to HTML and its tags match those found in HTML—there is a one-to-one mapping.

---

## Files

Markdown files are simply plain text files. But often the extension of the file is changed to `.md` to signify Markdown syntax.

---

## Use

One of the most common uses for Markdown files is Readmes. You’ll notice that GitHub will render your Markdowned Readme file and present it in a styled view. Just name your Readme `README.md` and GitHub will do the rest.

GitHub actually uses Markdown in lots of places including: issues and wikis.

Another really common use is content preparation for responsive websites. It’s a really good way to organize and understand the structure of content without forcing HTML upon your authors.

---

## Syntax

For paragraphs in Markdown there is no visible syntax,
just write lines of text and separate them by a blank line.
Markdown will automatically convert text with blank lines between into paragraphs.

### Paragraphs

```markdown
This is the first paragraph.

This is the second paragraph of text.
```

### Bold & italic

To make something italic, surround it in a single set of asterisks.
To make something bold, surround it in double asterisks.

```markdown
Some words are *italic* and some words are **bold**.
```

### Headings

Headings are denoted using a hash symbol in front:

```markdown
# Heading level 1
## Heading level 2
### Heading level 3
```

### Lists

Lists are created by putting dashes in front of lines of text:

```markdown
- List item 1
- List item 2
- List item 3
```

If you want to make an ordered list, instead use numbers:

```markdown
1. Item A
2. Item B
3. Item C
```

### Links

To add links there is a little more syntax:

```markdown
[Link this text](http://url-to-link-to.com/)
```

### Images

To add images, use a syntax similar to links:

```markdown
![Image alt attribute](http://url-to-image.com/image.png)
```

### Horizontal rules

To add horizontal rules, use three dashes:

```markdown
This is a paragraph.

---

This is another paragraph, separated by a horizontal rule.
```

### Code

Inside Markdown, code samples can be written two ways:

**Inline** — written inside other text with a single backtick:

```markdown
The `<h1>` tag denotes the most important text on the page.
```

**Code blocks** — starting with 3 backticks and ending with 3 more backticks:

<pre><code>```
&lt;h1&gt;Dinosaurs!&lt;/h1&gt;
```</code></pre>

With code blocks you can even specify the syntax by writing it directly after the 3 starting backticks:

<pre><code>```html
&lt;h1&gt;Dinosaurs!&lt;/h1&gt;
```</code></pre>

### Task lists

And finally, GitHub supports task lists in Markdown files using the following format:

```markdown
- [ ] Thing to do
- [ ] Another thing to do
- [x] Thing that’s already done
```

*GitHub will even convert those to checkboxes in specific locations.*

---

## Video list

1. [Markdown: applications](https://www.youtube.com/watch?v=a7RYPhsj1Js&index=1&list=PLWjCJDeWfDdeCy2wlIbAVfY4dLJx58ghX)
2. [Markdown: syntax basics](https://www.youtube.com/watch?v=0_tO8HgJiLQ&index=2&list=PLWjCJDeWfDdeCy2wlIbAVfY4dLJx58ghX)
3. [Markdown: inserting links](https://www.youtube.com/watch?v=0aJCGOxeHVk&index=3&list=PLWjCJDeWfDdeCy2wlIbAVfY4dLJx58ghX)
4. [Markdown: inserting images](https://www.youtube.com/watch?v=afFb_DcBBdA&index=4&list=PLWjCJDeWfDdeCy2wlIbAVfY4dLJx58ghX)
5. [Markdown: inserting code samples](https://www.youtube.com/watch?v=6nxjPtXHOYo&index=5&list=PLWjCJDeWfDdeCy2wlIbAVfY4dLJx58ghX)
6. [Markdown: task lists](https://www.youtube.com/watch?v=-JB6KEUj7tY&index=6&list=PLWjCJDeWfDdeCy2wlIbAVfY4dLJx58ghX)

## Supplemental links

- [GitHub: Mastering Markdown](https://guides.github.com/features/mastering-markdown/)
- [GitHub Flavored Markdow](https://help.github.com/articles/github-flavored-markdown/)
- [Wikipedia: Markdown](http://en.wikipedia.org/wiki/Markdown)
- [Markdown Spec](http://daringfireball.net/projects/markdown/)
- [Markdown Basics](http://daringfireball.net/projects/markdown/basics)
- [Markdown Syntax](http://daringfireball.net/projects/markdown/syntax)
- [CommonMark](http://commonmark.org/)
- [10 Useful Resources for Learning Markdown Syntax](http://sixrevisions.com/resources/learning-markdown-syntax/)
- [Learning Markdown: My Gateway into Coding](http://blog.teamtreehouse.com/learning-markdown-gateway-coding)
- [Google documentation guide](https://github.com/google/styleguide/tree/gh-pages/docguide)

### Markdown apps

- **[IA Writer](http://www.iawriter.com/)**
- **[Marked](http://markedapp.com/)**
- [Markdown Preview (Chrome extension)](https://chrome.google.com/webstore/detail/markdown-preview/jmchmkecamhbiokiopfpnfgbidieafmd)
- [Markdown Live Preview](http://markdownlivepreview.com/)
- [Markdown Preview (Atom)](https://atom.io/packages/markdown-preview)
- [Markdown Preview (Sublime)](https://packagecontrol.io/packages/Markdown%20Preview)
- [MarkdownPad](http://www.markdownpad.com/)
- [Mou](http://mouapp.com/)
- [Dingus](http://daringfireball.net/projects/markdown/dingus)
- [Byword](http://bywordapp.com/)
- [Writage](http://www.writage.com/)
- [The Best Markdown Editor for Windows](http://www.sitepoint.com/best-markdown-editors-windows/)
