---
title: "Modules"
tags: "modules object oriented css reuse list group buttons icons media object embed containers bem smacss oocss"
desc: "Abstractions for common website patterns that can be reused in many situations."
playlist: modules
download: https://github.com/learn-the-web/modules-code/archive/master.zip
github: https://github.com/learn-the-web/modules-code
cheatsheet: modulifier-cheat-sheet
tool:
  name: Modulifier
  url: "https://modulifier.web-dev.tools"
extra_practice:
  week:
    title: "Web Dev 2, Week 07"
    url: "/courses/web-dev-2/week-07/"
  slides:
    - title: "Modular CSS"
      url: "/courses/web-dev-2/modular-css/"
  lessons:
    - title: "Button systems"
      url: "/courses/web-dev-2/button-systems/"
  activities:
    - title: "Module Mogul"
      url: "module-mogul"
  exercises:
    - title: "Embed containers"
      url: "/courses/web-dev-2/week-07/#embed-containers"
    - title: "Icons"
      url: "/courses/web-dev-2/week-07/#icons"
    - title: "List groups"
      url: "/courses/web-dev-2/week-07/#list-groups"
---

Thinking modularly in CSS allows us to create more reusable CSS. And allows us to really reduce our duplication making our code more maintainable.

---

## Why is modularity important?

When writing CSS, and any code, we want to make everything as lean and maintainable as possible. In code there’s a common idiom: “Keep it DRY”; meaning don’t repeat yourself.

When writing code, don’t just think about what makes sense now, but also think about what makes sense in the future.

- If you come back to a project in a year, will you know what’s going on?
- If you give your code to another person is it obvious where everything is?
- If you find yourself copying and pasting code from one place to another, you have a problem.
- If you find that two elements have nearly identical code, combine them together.
- If you find something that feels *wrong* or *hacky*, see if there’s a better way.

---

## Ways to simplify CSS

When looking at simplifying your CSS there a few things you can consider:

- Look for common properties, like text alignment, margins, paddings, etc.
- Look for common patterns, common design items with small variations, like buttons, or horizontal lists, and extract those into reusable classes.
- Use min-width media queries so you don’t have to copy and paste all your CSS into each new MQ.

If you’re using a [grid system](https://gridifier.web-dev.tools) or the [modular type system](https://typografier.web-dev.tools), they often come with a bunch of abstracted CSS classes to help you out.

Some utility classes you could consider:

- `.left`, `.right` to float elements.
- `.text-left`, `.text-center`, `.text-right` to change the text alignment.
- `.bold`, `.italic` to change the font weight and style.
- `.gutter`, `.island` for consistent padding.
- `.push` for consistent margins.
- `.img-flex` to make images responsive.

*But be really careful not to go overboard—these classes should be considered “brute-force” and used within reason.*

### Example: list group

A very common pattern in websites is using lists because they semantically make sense but not wanting them to have bullets. This is called a “list group”.

Here’s a simple navigation, almost always a list, but rarely with bullets.

```html
<nav>
  <ul class="nav list-group">
    <li><a href="#">Terrestrial planets</a></li>
    <li><a href="#">Gas giants</a></li>
    <li><a href="#">Dwarf planets</a></li>
    <li><a href="#">Asteroids</a></li>
  </ul>
</nav>
```

We can use the `.list-group` class as a way to simplify, always removing the padding and bullets from a list.

```css
.list-group {
  padding-left: 0;
  list-style-type: none;
}
```

Another common thing we want with lists is to make the `<li>` elements horizontal, instead of stacked, called “inline list group”.

```html
<nav>
  <ul class="nav list-group list-group-inline">
    ⋮
```

Then with a little bit extra CSS we can have a list with no bullets and inline.

```css
.list-group-inline > li {
  display: inline-block;
}
```

Notice how I kept the two classes separate, so we could remove the bullets with one class, and make the items horizontal with another class.

### Example: buttons

Another great place to look for simplification is with buttons.

Here’s an example of a simple button:

```html
<a class="btn" href="#">Go!</a>
```

Here’s some standard CSS for a button:

```css
.btn {
  display: inline-block;
  padding: 0.5em 0.75em;
  background-color: red;
  border: 3px solid darkred;
  color: #fff;
  text-decoration: none;
}
```

Now, if I wanted a differently coloured button, it’s unnecessary to create a whole second class with duplicated CSS, I can just make a slight modifier class:

```css
.btn-bright {
  /* I only change those properties that are different */
  background-color: yellow;
  border-color: darkyellow;
  color: #000;
}
```

And apply it to my HTML like this:

```html
<a class="btn btn-bright" href="#">Go!</a>
```

So now the button inherits all the CSS from the standard `.btn` class plus the slightly modified `.btn-bright` class—creating much less duplicated CSS.

If you have a [modular type system](https://typografier.web-dev.tools) you can use the font-size classes to adjust the size of the button with another class:

```html
<!-- Inheriting the .mega class from the type system -->
<a class="btn btn-bright mega" href="#">Go!</a>
```

---

## Common website modules

- **[List group](https://demos.learntheweb.courses/modules/list-group.html)**: vertical & horizontal lists.
- **[Buttons](https://demos.learntheweb.courses/modules/buttons.html)**: small, medium, large, alternative, [buttons + modular typography](https://demos.learntheweb.courses/modules/buttons-modular-type.html).
- **[Icons](https://demos.learntheweb.courses/modules/icons.html)**: different sizes, stacked, inline, image replacement.
- **[Media object](https://demos.learntheweb.courses/modules/media-object.html)**: flexible image size, embeddable, with list group, stacked, reversed.
- **[Embed containers](https://demos.learntheweb.courses/modules/embed.html)**: for flexible images and videos, with specific aspect ratios—to prevent layout reflow after the image loads.

*The `common.css` file used in the examples and videos could be replaced by your modular typography `typography.css` file for better results.*

---

## Naming conventions

There are a couple major naming conventions for modular CSS that help clarify the intent of our classes and help us visualize the HTML by just looking at the CSS classes.

- When we looked at icons, that naming system comes from [**SMACSS**](http://smacss.com/).
- The [**BEM**](http://bem.info/) naming convention takes naming a little further by using double underscores or double hyphens to represent certain ideas—this can be seen in the embed containers.

**Links**

- [Getting Your Head Around BEM Syntax](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)

---

## Generated modules & patterns

You probably don’t want to write all these same CSS patterns, or try and find them and copy and paste them from previous websites, every time you make a new website.

[**Check out Modulifier**](https://modulifier.web-dev.tools/), a tool I created for myself to generate the code for these patterns & modules and many other things I like to include *by default* on every website I make.

---

## Video list

1. [Modules: List group](https://videos.learntheweb.courses/playlists/modules/#1-list-group)
2. [Modules: Buttons](https://videos.learntheweb.courses/playlists/modules/#2-buttons)
3. [Modules: Making modular icons](https://videos.learntheweb.courses/playlists/modules/#3-icons)
4. [Modules: Combining the icons and the list group](https://videos.learntheweb.courses/playlists/modules/#4-icons-inline)
5. [Modules: Icon image replacement](https://videos.learntheweb.courses/playlists/modules/#5-icons-image-replacement)
6. [Modules: Media object](https://videos.learntheweb.courses/playlists/modules/#6-media-object)
7. [Modules: Combining the media object and the list group](https://videos.learntheweb.courses/playlists/modules/#7-media-object-list-group)
8. [Modules: Media object alternatives](https://videos.learntheweb.courses/playlists/modules/#8-media-object-alternative)
9. [Modules: Embed containers](https://videos.learntheweb.courses/playlists/modules/#9-embed-img)
10. [Modules: Embedding videos responsively](https://videos.learntheweb.courses/playlists/modules/#10-embed-video)
11. [Modules: Embed containers with figures](https://videos.learntheweb.courses/playlists/modules/#11-embed-figure)
12. [Modules: Combining buttons with modular typography](https://videos.learntheweb.courses/playlists/modules/#12-buttons-typography)
13. [Modules: Using Modulifier](https://videos.learntheweb.courses/playlists/modules/#13-modulifier)

## Supplemental links

- [OOCSS](https://github.com/stubbornella/oocss/wiki)
- [An Introduction to OOCSS](http://coding.smashingmagazine.com/2011/12/12/an-introduction-to-object-oriented-css-oocss/)
- [The Flag Object](http://csswizardry.com/2013/05/the-flag-object/)
- [CSS Wizardry: CSS Guidelines](https://github.com/csswizardry/CSS-Guidelines)
- [Responsive Images: How to Prevent Reflow](http://andmag.se/2012/10/responsive-images-how-to-prevent-reflow/)
- [Back to the :roots](http://simurai.com/blog/2015/09/09/back-to-the-roots)
