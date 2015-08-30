---
group: web-dev-4
playlist: PLWjCJDeWfDdfzjgthWhvHOxyvFZDCp_2L
download: https://github.com/acgd-learn-the-web/yaml-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/yaml-code
cheatsheet: markdown-yaml-cheat-sheet
---

Yet Another Markup Language (YAML) is a way to create structured text and data—often used for generating websites and configuration.

---

## What’s the point of YAML

YAML’s simple structure is great work creating [☛ content templates](/topics/writing-for-the-web/#content-templates) and for making systems of website generation.

When using a system like [☛ Jekyll](/topics/jekyll/), YAML can bet used for extra metadata about the document that isn’t part of the main content, that can be used in different places.

A couple examples:

- [This tutorial uses YAML, see the source code](https://github.com/acgd-learn-the-web/topics/blob/master/yaml/index.md)
- [The Markdown & YAML cheat sheet is written in YAML, see the code](https://github.com/acgd-learn-the-web/topics/blob/master/markdown-yaml-cheat-sheet/index.md)

---

## Indent with spaces

**YAML is really strict about this: indent with 2 spaces only.**

---

## Structured data

YAML is for structuring data and information using systems like objects and arrays from programming languages.

The data of YAML has two main structures:

- **objects:** like `<dl>` elements in HTML, or `{}` objects in Javascript
- **arrays:** like `<ul>` elements in HTML, or `[]` arrays in Javascript

## Objects

Objects in YAML are started with a word/term followed by a colon and space. You make up the term so that it suits your data.

```yaml
name: Tyrannosaurus
```

We can have as many items in the object as we want:

```yaml
name: Tyrannosaurus
period: Late Cretaceous
age: 160
```

We can even have objects inside other objects, just by starting a new term:

```yaml
dimensions:
  width: 3 metres
  height: 8 metres
  length: 12 metres
  weight: 4 tonnes
```

## Arrays

Arrays are just a big list or collection, each item starting with a dash. They keep their order when output in systems.

```yaml
likes_to_eat:
  - Other dinosaurs
  - Meat
  - More meat
  - Not plants
```

Above you can see that the array is inside an object. But it can be the other way around too, objects inside arrays:

```yaml
- name: T. rex
  period: Late Cretaceous Period
- name: Stegosaurus
  period: Late Jurassic Period
- name: Velociraptor
  period: Cretaceous Period
```

---

## Text blocks

If you have super large text blocks in your YAML, you can use vertical pipes (`|`) or greater than symbols (`>`) to separate the text out and allow a little more formatting.

### Greater than

The greater than symbol allows you to write your text on multiple lines, knowing that when your YAML is parsed those lines will be collapsed into a single line.

```yaml
desc: >
  Tyrannosaurus (/tɨˌrænəˈsɔrəs/ or /taɪˌrænəˈsɔrəs/ ("tyrant lizard", from the Ancient Greek tyrannos (τύραννος), "tyrant", and sauros (σαῦρος), "lizard"[1])) is a genus of coelurosaurian theropod dinosaur.
  The species Tyrannosaurus rex (rex meaning "king" in Latin), commonly abbreviated to T. rex, is one of the most well-represented of the large theropods.
```

### Vertical pipe

The vertical pipe allows you to write your text on multiple lines, knowing that those multiple lines will be kept when the YAML is parsed.

```yaml
poem: |
  T. rex, T.rex
  How I love thee
```

The vertical pipe is really great for embedding code samples in YAML:

```yaml
code: |
  <div>
    <h1>Things</h1>
    <p>Things....</p>
  </div>
```

---

## Escaping information

Sometimes YAML can get confused between content and structure—like for instance when using ampersands. If that’s the case, we can wrap the content in quotes to escape it.

```yaml
name_meaning: "tyrant & lizard"
```

---

## Markdown front matter

We use Markdown for structuring our content, but sometimes you want to add more structured data to your Markdown that just the default formatting. This can be accomplished with YAML front matter.

At the top of your Markdown document, you put a series of three double dashes and provide more data between them:

```yaml
---
name: Venus
discoverer: Galileo Galilei
discovered: 1610
orbit: 247 days
radius: 6051 km
tilt: 177°
---
```

This data can then be used in lots of applications, including Jekyll.

---

## Video list

1. [YAML: syntax basics](https://www.youtube.com/watch?v=W3tQPk8DNbk&list=PLWjCJDeWfDdfzjgthWhvHOxyvFZDCp_2L&index=1)
2. [YAML: text blocks](https://www.youtube.com/watch?v=m-rRIsuekBw&list=PLWjCJDeWfDdfzjgthWhvHOxyvFZDCp_2L&index=2)
3. [YAML: Markdown front matter](https://www.youtube.com/watch?v=GOcgJgrxeJ4&list=PLWjCJDeWfDdfzjgthWhvHOxyvFZDCp_2L&index=3)

## Supplemental links

- **[YAML Validator](http://yamllint.com/)**
- [Wikipedia: YAML](http://en.wikipedia.org/wiki/YAML)
- [YAML Spec](http://yaml.org/)
- [YAML Front Matter](http://jekyllrb.com/docs/frontmatter/)
