---
title: "Pattern libraries"
tags: "css style guides pattern library libraries templates themes tiles components modules systems mood boards"
desc: "A quick tutorial on making pattern libraries & component systems for websites with a bunch of helpful links."
playlist: PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0
download: https://github.com/acgd-learn-the-web/jekyll-patternbot-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/jekyll-patternbot-code/
livewebsite: https://stoic-engelbart-a37d1e.netlify.com/pattern-library/
cheatsheet: pattern-library-cheat-sheet
---

Pattern libraries—or style guides—are a great tool when working on teams. We can communicate documentation of all the different website components, show how & when to use them and really see an overview of what’s available to build out a website.

---

## Installation & setup

There are lots of different pattern library generation systems with lots of different features. This tutorial will concentrate on [Jekyll Patternbot](https://github.com/thomasjbradley/jekyll_patternbot) which is a plugin for [Jekyll](https://jekyllrb.com/) & therefore built with [Ruby](https://www.ruby-lang.org/en/).

### Tool installation

In order to get everything working there’s a bunch of stuff we need to install on our computers.

[**☛ Follow this step-by-step lesson to install all the developer tools**](/courses/web-dev-4/install-more-developer-tools/)

### Basic setup

After you’ve got all that installed we still need to set up our folder with a few important files.

[**☛ Work through this step-by-step lesson on the basic setup**](/courses/web-dev-4/pattern-library-set-up/)

### Hosting on Netlify

Even though we’re using Jekyll & it’s supported by GitHub, Jekyll Patternbot is not supported. We need to use another web-host that gives us more control over the tools we want to use.

Netlify is a good choice: they have a good CDN, a build process we can configure, free for small sites & some nice features.

[**☛ Check out this step-by-step lesson on setting up Netlify hosting**](/courses/web-dev-4/pattern-library-hosting/)

---

## Starting & stopping

Jekyll & Patternbot are command-line tools, meaning we can only use them through our Terminal application. We also have to keep Jekyll running in the background in Terminal when we’re working on our website.

### Starting

Inside GitHub Desktop, go to the `Repository` menu and press `Open in Terminal`—this will open the Terminal app and point it to the correct folder.

![](open-in-terminal.jpg)

Once Terminal is open to the correct folder we can type this command: `bundle exec jekyll serve`—then hit `Return`.

![](jekyll-serve.jpg)

Running this command will start Jekyll. **You must keep the Terminal window active for your website to function.** You can minimize the window if you’d like. If you close the Terminal window Jekyll will stop running and your website will be inaccessible.

I’ve highlighted in the Terminal window an important bit: that’s the URL where you must view your website. So, let’s pop it open:

[**☛ http://localhost:4000**](http://localhost:4000)

*The IP address `127.0.0.1` and `localhost` are interchangeable—I just find `localhost` much easier to type.*

### Stopping

To top the process in Terminal press `⌃C` (`Control-C`)—this will stop Jekyll from running & you’ll no longer be able to see your pattern library in the browser.

### Re-starting

Restarting Jekyll is very simple. Open in Terminal again, but instead of typing the command, press the `Up` arrow. It’ll go through the command history. When you see `bundle exec jekyll serve` just hit `Return`

---

## Theme

A good place to start our pattern library is by defining colours & CSS variables—and setting up our CSS itself.

Start by creating a CSS file named `theme.css` and putting it into your CSS folder.

### Defining colours

At the top of your `theme.css` is a good place to add CSS variables. Patternbot recognizes variables that start with `--color` & `--font` and will use those in the component library.

```css
:root {
  --color-primary: goldenrod;
  --color-primary-light: gold;
  --color-secondary: lightcoral;
  --color-secondary-dark: coral;
}
```

- `--color-primary` is treated as the most important colour.
- `--color-secondary` is treated as the second most important colour.
- `--color-neutral` & `--color-accent` are grouped.

### Adding fonts

It’s a good idea to also add your fonts into the `:root` declaration:

```css
:root {
  ⋮
  --font-primary: "Alegreya Sans", "Trebuchet MS", Arial, sans-serif;
  --font-secondary: "Source Code Pro", Menlo, Consolas, monospace;
}
```

Patternbot recognizes `--font-primary`, `--font-secondary` as important fonts. But other names work just as well.

If these are Google or Typekit fonts you’ll also want to pop that into your `_config.yml`

```yml
patternbot:
  font_url: "https://fonts.googleapis.com/css?family=Overpass:400,400i,700|Source+Code+Pro:400,700"
```

### Adding Web Dev Tools

Go ahead and get copies of all three Web Dev Tools naming the same we normally do:

- `css/modules.css` — [Modulifier](http://modulifier.web-dev.tools/)
- `css/grid.css` — [Gridifier](http://gridifier.web-dev.tools/)
- `css/type.css` — [Typografier](http://typografier.web-dev.tools/)

### Basic styles

Put all the site-wide, basic styles within your `theme.css` file. Like heading colours, link colours, body copy colours, etc.

### Combine into a mega CSS file

Make a new CSS file named `main.css` this is going to be a mega combination of all your CSS files & this is the file that Patternbot actually looks for.

*Inside your main.css file we’re going to add a little bit of Jekyll code.* This code instructs Jekyll to load all the other CSS files into this file—therefore combining them together into a single file.

```liquid
---
---
{% raw %}
{% include_relative modules.css %}
{% include_relative grid.css %}
{% include_relative type.css %}
{% include_relative theme.css %}
{% pattern_css %}{% endraw %}
```

**Yes! Those two lines of triple dashes are important.** This code says:

1. Get `modules.css` and place it here
1. Get `grid.css` and place it here
1. Get `type.css` and place it here
1. Get `theme.css` and place it here
1. Find all the pattern CSS files and place them here [(discussed this below)](#patterns)

---

## Customization

We can customize how Patternbot generates your component library. By default, Patternbot will use things like `--color-primary`, `--color-secondary`, `--font-primary`, `--font-secondary` as part of its interface to make the component library match the theme.

But we can customize a little further using some configuration options. Open up your `_config.yml` file and underneath the `patternbot` entry try these options out:

```yml
patternbot:
  title: "Dino Rescue"
  description: |
    A small local dinosaur rescue organization specializing in herbivores. Dinos are in danger and we need to save them all!
```

- `title` — allows us to change the title at the top of the pattern library
- `description` — allows us to change the introduction paragraph

### Interface colours

Taking the configuration a little further we can change the colours Patternbot uses in the component library interface:

```yml
patternbot:
  colors:
    background: "--color-neutral"
    accent: "--color-primary"
```

- `background` — configures the background colour of the whole document from the default of white
- `accent` — instead of using `--color-primary` as the heading & accent colour for the interface

*Variable names work. But do just plain old hex-colours.*

### Rationales

One of the major parts of making a pattern library is documentation: documenting when & how to use the patterns, and when to use fonts and colours.

Since Patternbot automatically pulls fonts and colours into its interface, we can write rationales for them inside `_config.yml`:

```yml
patternbot:
  rationales:
    typefaces.primary: |
        The primary typeface represents clarity and simplicity. It should be used for just about everything.
    typefaces.secondary: |
        The secondary typeface is specifically for code samples within the website.
    colors.primary: |
        Well it’s red because why not.
    colors.secondary: |
        This colour was chosen because it’s complementary to red. It should be used sparingly for little punches of difference.
```

Add a new entry inside `patternbot` named `rationales`. Within that you can write rationales for the specific fonts & colours.

If your variable is `--color-primary` the rationale entry will be `colors.primary`, etc. & similarly for fonts and typefaces.

---

## Logos & icons

Patternbot is pretty smart about logos and icons and will go looking for them within your folder.

### Logo sizes & variations

For logos, name your files like this:

- `images/logo.svg`
- `images/logo-64.svg`
- `images/logo-32.svg`
- `images/logo-16.svg`

Patternbot will show those in the interface to help you show off the different sizes & variations for the logo.

### Icon spritesheets

If you have an icon spritesheet name the file `icons.svg` and plop it into your `images` folder and Patternbot will pick out the icons to display nicely.

---

## Patterns

### Configuring patterns

### Patterns inside patterns

### Datasets

### Using patterns

---

## Sample pages

To show-off how the patterns look together inside full pages you can create some sample pages.

Make a new folder named `sample-pages` and drop some HTML files in there—the names will pop-up into Patternbot’s menu.

---

## It’s all Jekyll

**Remember that Patternbot is built on top of Jekyll—many of its features are just features of Jekyll.** You can integrate Jekyll & Patternbot features together perfectly well.

---

## Video list

- [Jekyll + Patternbot: installation & setup](https://www.youtube.com/watch?v=Vptn8zl0gXY&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=2&t=0s)
- [Jekyll + Patternbot: hosting on Netlify](https://www.youtube.com/watch?v=OAEntDQoXp4&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=3&t=0s)
- [Jekyll + Patternbot: starting & stopping](https://www.youtube.com/watch?v=DJT1rvCbBKw&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=4&t=2s)
- [Jekyll + Patternbot: theme colours](https://www.youtube.com/watch?v=ARF3TfYLX20&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=5&t=0s)
- [Jekyll + Patternbot: theme fonts](https://www.youtube.com/watch?v=7XuDk8WqG4M&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=6&t=3s)
- [Jekyll + Patternbot: Web Dev Tools](https://www.youtube.com/watch?v=FtbzdKzj6B0&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=7&t=0s)
- [Jekyll + Patternbot: basic theme styles](https://www.youtube.com/watch?v=1W2ERDOUiz0&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=8&t=0s)
- [Jekyll + Patternbot: CSS utility classes](https://www.youtube.com/watch?v=VjHqyXvsALc&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=9&t=0s)
- [Jekyll + Patternbot: design customization](https://www.youtube.com/watch?v=VgcOBkLj4Zw&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=10&t=0s)
- [Jekyll + Patternbot: rationales](https://www.youtube.com/watch?v=DPEnBjY15QU&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=11&t=0s)
- [Jekyll + Patternbot: logos](https://www.youtube.com/watch?v=_ufPySL7d3c&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=12&t=0s)
- [Jekyll + Patternbot: icons](https://www.youtube.com/watch?v=LytJfBk94a4&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=13&t=0s)
- [Jekyll + Patternbot: simple pattern](https://www.youtube.com/watch?v=itzCGl2gS2c&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=14&t=0s)
- [Jekyll + Patternbot: pattern config](https://www.youtube.com/watch?v=AuZ6lowg0MQ&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=15&t=0s)
- [Jekyll + Patternbot: patterns inside patterns](https://www.youtube.com/watch?v=kGWFTSX-E2s&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=16&t=0s)
- [Jekyll + Patternbot: layouts](https://www.youtube.com/watch?v=KcScysgw2yU&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=17&t=0s)
- [Jekyll + Patternbot: datasets](https://www.youtube.com/watch?v=LigllyxKYuE&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=18&t=0s)
- [Jekyll + Patternbot: sample pages](https://www.youtube.com/watch?v=fqqid3NV3Gs&list=PLWjCJDeWfDdcEBngBwpB8F7wtjZ12PIy0&index=19&t=0s)

## Supplemental links

- [**StyleGuides.io**](http://styleguides.io/)
- [**Content Modeling With Jekyll**](https://www.smashingmagazine.com/2016/02/content-modeling-with-jekyll/)
- [Style Guide Generator Roundup · An A List Apart Blog Post](https://alistapart.com/blog/post/%7Bhttps://alistapart.com/blog/post/style-guide-generator…)
- [Adele - Design Systems and Pattern Libraries Repository](https://adele.uxpin.com/)

### Amazing pattern libraries

- [**MailChimp Pattern Library**](http://ux.mailchimp.com/patterns)
- [**HMCTS Design System**](http://hmcts-design-system.herokuapp.com/)
- [U.S. Web Design System](https://designsystem.digital.gov/)
- [GitHub Style Guide](https://styleguide.github.com/primer/utilities/borders/)
- [Walmart Styleguide](https://walmartlabs.github.io/web-style-guide/)

### Awesome tools

- [Styleguide generators](https://github.com/davidhund/styleguide-generators/blob/master/README.md)
- [Fabricator](https://fbrctr.github.io/)
- [Pattern Lab](http://patternlab.io/)
- [Styleguide](https://hugeinc.github.io/styleguide/)
- [Catalog](https://www.catalog.style/?mc_cid=545e488581&mc_eid=fe2644e9d7)
