---
title: "Jekyll"
tags: "jekyll layouts templates header footer github combine separate"
desc: "Reducing code duplication in website by using templates and layouts with Jekyll."
playlist: jekyll
download: https://github.com/learn-the-web/jekyll-code/archive/gh-pages.zip
github: https://github.com/learn-the-web/jekyll-code
livewebsite: jekyll
cheatsheet: jekyll-cheat-sheet
---

Jekyll is a static website generator—it helps making websites more efficient by reducing duplication.

---

## Why use Jekyll?

The main reasons for using Jekyll are efficiency, it eliminates lots of copying and pasting in our websites amoung other things:

- Makes use of [**☛ Markdown**](/topics/markdown/) to reduce the overhead of HTML,
- Allows sharing of HTML code between pages,
- Has the ability to automatically write repeated HTML,
- Can be hosted on GitHub using GitHub pages.

*Jekyll isn’t the only way to get these features, you could use other static site generators or even other languages like PHP, Python, or Ruby.*

---

## Jekyll Installation

Jekyll is a command line tool, it requires the Apple command line tools to be installed.

[**☛ Check out the Jekyll installation guide.**](/topics/jekyll-installation/)

**Links**

- [Jekyll Docs: installation](http://jekyllrb.com/docs/installation/)

---

## Setting up Jekyll

To set up a Jekyll project you must add a file named `_config.yml`. Put this directly in your folder, in the same place as your `index.html` file.

Here’s a sample config file:

```yaml
permalink: pretty
baseurl: /your-folder-on-github
```

*After you have your config file, you can run Jekyll in the Terminal.*

**Links**

- [**☛ Setting up GitHub Pages Reference**](/topics/version-control-github/#setting-up-hosting-with-github-pages)
- [Jekyll Docs: Directory structure](http://jekyllrb.com/docs/structure/)
- [Jekyll Docs: Configuration](http://jekyllrb.com/docs/configuration/)

---

## Running Jekyll

Jekyll must be running in the Terminal when you are actively developing a project. Every time you save a file, Jekyll does its stuff to the file and copies it to the `_site` folder, where the final version of the website is found.

[**☛ Check out the Jekyll terminal guide.**](/topics/jekyll-terminal-guide/)

**Links**

- [Jekyll Docs: Quick-start guide](http://jekyllrb.com/docs/quickstart/)
- [Jekyll Docs: Usage](http://jekyllrb.com/docs/usage/)

---

## The _site folder

When Jekyll is running and you save one of your files it will be copied to the `_site` folder. The `_site` folder is completely temporary, but is also the final, compiled version of your website.

*If you delete the `_site` folder, when you save a file again it will immediately come back.*

### Never have the _site folder on GitHub

Since the `_site` folder is temporary it should *never be committed to GitHub.*

Git has a method for ignoring files, so that they can never be accidentally committed.

If you create a new file named `.gitignore`, in the same location as your `index.html` Git will look here for what files and folders to hide.

Inside the `.gitignore` file you can write the folder you want to hide, like this:

```
_site
```

Commit it into your repository and Git will safely ignore the `_site` folder from now on.

[**☛ Read more about .gitignore.**](/topics/version-control-github/#ignoring-files)

---

## Layouts

Jekyll has a feature named layouts that allows designers to put the header and footer in a single file and have them shared between every page on the site—kind of like master pages in InDesign.

This is probably one of the most compelling reasons to use Jekyll.

First open you `index.html` file and look for stuff that will be common to every page, like headers, footers, DOCTYPE, etc.

Cut that stuff and put it into a new file: `default.html`. It doesn’t have to be called “default”, that’s just a convention.

*Save this file into a folder named `_layouts`.*

```
_config.yml
_layouts/        ⬅︎ The layouts folder
  └ default.html
index.html
```

The file might look something like this:

```html
<!DOCTYPE html>
<html lang="en-ca">
<head>
  <meta charset="utf-8">
  <title>Website</title>
</head>
<body>
  <header>
    <h1></h1>
    <nav></nav>
  </header>

  <main>
    {% raw %}{{content}}{% endraw %}
  </main>

  <footer>
    <p>©</p>
  </footer>
</body>
</html>
```

The {% raw %}`{{content}}`{% endraw %} placeholder is where Jekyll will place the content from the `index.html`.

Then, inside your `index.html`, all you’ll have left is this:

```html
<h1>Homepage</h1>
```

Jekyll doesn’t magically know what layout to use, so at the top of our `index.html` file we need to include a little [**☛ YAML**](/topics/yaml/) to Jekyll where to find the layout.

```html
---
layout: default
---

<h1>Homepage</h1>
```

And that’s it. If you want to make a second page all you have to do is include the YAML front matter and the layout will automatically be applied to your new page.

### Nested layouts

With Jekyll we can even have layouts that fit into other layouts. An example of when this is helpful is if you have a sub section of your website with a common navigation, but it still has the websites main navigation.

In our `_layouts` folder we just need to make two files, like this:

```
_layouts/
  └ default.html
  └ sub-section.html
```

Our sub-section page, would point to the `sub-section` layout, like this:

**page.html**

```yaml
---
layout: sub-section
---
```

Then, the `sub-section.html` layout file would point to default, like this:

**sub-section.html**

```yaml
---
layout: default
---
```

### Passing information from pages to layouts

Using the YAML at the top of pages we can send information up to the layout to populate specific fields:

**page.html**

```yaml
---
layout: default
title: Amazing dinosaurs!
bodyClass: dinos-page
---
```

Then, inside our `default.html` layout we can use that information wherever we want:

**default.html**

```html
{% raw %}<!DOCTYPE html>
<html lang="en-ca">
<head>
  <meta charset="utf-8">
  <title>{{page.title}}</title>
</head>
<body class="{{page.bodyClass}}">
⋮ {% endraw %}
```

We have variables in two places: {% raw %}`{{page.title}}`{% endraw %} and {% raw %}`{{page.bodyClass}}`{% endraw %} that are basically placeholders, waiting for the information from the page.

*Notice how the name of the variables is prepended by the `page.`, indicating that the information is coming from the top of the page itself.*

**Links**

- [Jekyll Docs: Templates](http://jekyllrb.com/docs/templates/)

---

## Linking to other pages

If you’re using the `permalink: pretty` setting in you `_config.yml`—which I suggest doing—then linking to pages is slightly different from normal.

Usually we link directly to the HTML file, with the HTML extension, but Jekyll is actually making a folder for each page in order to hide the HTML extension from the URL. So, we only need to link to the folder.

If we have a folder setup like this:

```
_config.yml
_layouts/
  └ default.html
index.html
about.html
contact.html
```

Then, the navigation inside our layout would look like this:

```html
<nav>
  <ul>
    <li><a href="/">Home</a></li>
    <li><a href="/about/">About</a></li>
    <li><a href="/contact/">Contact</a></li>
  </ul>
</nav>
```

*Notice how we’re haven’t included the `.html` extension in our URLs.*

### Base URLs

If you’re using GitHub as a host then your project is within a folder, when looking at it live on GitHub’s URL. But on your local computer there is no folder.

**On your local computer, the URL might look like this:**

```
http://127.0.0.1:4000/about/
```

**But on GitHub, it will look like this:**

```
http://dinos.github.io/meat-eaters/about/
```

*Notice the extra folder between the domain and the name of the page—this is the base URL.*

We even add the base URL into our `_config.yml` file when setting it up. But we still need to include it in our HTML for the navigation to work consistently across all locations.

```html
{% raw %}
<nav>
  <ul>
    <li><a href="{{site.baseurl}}/">Home</a></li>
    <li><a href="{{site.baseurl}}/plant-eaters/">Plant eaters</a></li>
    <li><a href="{{site.baseurl}}/meat-eaters/">Meat eaters</a></li>
  </ul>
</nav> {% endraw %}
```

*Notice the addition of {% raw %}`{{site.baseurl}}`{% endraw %}, this allows our local computer to not have the extra folder in the URL, but the remote GitHub host computer to include the extra folder.*

### Highlighting navigation

It’s good practice to highlight the navigation on the website to help your users understand where they are in the structure of the site.

Jekyll can do this with some if-statements inside our navigation’s `<a>` tags. The if-statements check what page is current then only add a class to the appropriate `<a>` tag.

```html
{% raw %}<a href="{{site.baseurl}}/plant-eaters/" {% if page.url == '/plant-eaters/' %} class="current" {% endif %}>Plant eaters</a>{% endraw %}
```

*The if-statement is wrapped around the `class="…"` attribute, therefore the class will only shown on the `<a>` tag when the page is active.* It can be styled in CSS just like normal.

---

## Linking images

Linking to images isn’t really that different from regular, but the addition of {% raw %}`{{site.baseurl}}`{% endraw %} makes them work more reliably across hosts.

```html
{% raw %}<img src="{{site.baseurl}}/images/trex.jpg" alt="">{% endraw %}
```

---

## Adding CSS

When making Jekyll websites, CSS works exactly the same as normal, because Jekyll is just outputting straight-up HTML—so, from the CSS’s perspective, Jekyll doesn’t actually exist.

But, it’s a good idea to link the CSS file with the {% raw %}`{{site.baseurl}}`{% endraw %} for reliably.

```html
{% raw %}<link href="{{site.baseurl}}/css/main.css" rel="stylesheet">{% endraw %}
```

---

## Data files

Data files are a great way to separate the content from the its presentation HTML. Data files are mostly written in YAML, but other languages can also be used.

First create a new folder in your Jekyll website named `_data`, put it in the same location as the `index.html` and the `_layouts` folder.

```
_config.yml
_data/       ⬅︎ The data folder
_layouts/
index.html
```

Then inside that folder make your data file, named with the `.yml` extension. Here’s an example data file:

**dinos.yml**

```yaml
- name: Tyrannosaurus
  diet: Meat
  size: Big
- name: Stegosaurus
  diet: Plants
  size: Medium
- name: Velociraptor
  diet: Meat
  size: Small
```

After we have the data file created we can use it in our website. The great thing about doing it this way is that we don’t have to copy and paste our HTML, Jekyll will do the work for us.

```html
{% raw %}{% for dino in site.data.dinos %}
  <h2>{{dino.name}}</h2>
  <dl>
    <dt>Diet</dt>
    <dd>{{site.diet}}</dd>
    <dt>Size</dt>
    <dd>{{site.size}}</dd>
  </dl>
{% endfor %}{% endraw %}
```

Using a `for` loop we’re looping over every entry in the data file. The `site.data.dinos` is how we access our data file—the `.dinos` part is exactly the name of the file.

Because there are three dinosaurs in the data file, Jekyll will automatically output the above HTML three times: once for each dinosaur.

**Links**

- [Jekyll Docs: Data Files](http://jekyllrb.com/docs/datafiles/)

---

## Includes

Includes are reusable pieces of HTML, akin to symbols in Illustrator. We can create one file with some HTML in it, then use that file in multiple locations. If we update the single file all uses will automatically get updated.

To create an include we first need to make the specialized folder: `_includes`. Put it in the same place as `_layouts` and `index.html`.

```
_config.yml
_includes/    ⬅︎ The includes folder
_layouts/
index.html
```

Then inside that folder make your HTML file, named with the `.html` extension. Here’s an example:

**button.html**

```html
<a class="btn" href="/go/">Go!</a>
```

In any of our Jekyll pages, we can use the include file to output whatever HTML is inside it:

**index.html**

```html
---
layout: default
---
{% raw %}{% include button.html %}
{% include button.html %} {% endraw %}
```

*Notice that we’re using the `include` tag to bring in the HTML twice into the file.*

### Include parameters

With the above (very simple) example, there’s a small issue: both buttons would say “Go!” and point to the same page. We can overcome this limitation by using include parameters.

First, we change our include to have place holders in it, like this:

**button.html**

```html
{% raw %}<a class="btn" href="{{include.url}}">{{include.text}}</a>{% endraw %}
```

*Notice that we changed the variable sections to place holders {% raw %}`{{include.url}}`{% endraw %} and {% raw %}`{{include.text}}`{% endraw %}.* The `include.` part indicates the information is coming from an include. The part that comes after the dot is just made up.

Now, in our HTML we can adjust the includes to have the variable information:

**index.html**

```html
---
layout: default
---
{% raw %}{% include button.html url="/prev/" title="Previous" %}
{% include button.html url="/next/" title="Next" %}{% endraw %}
```

*My example above is extremely simple, and probably doesn’t make sense to do for a button (because the include code is practically the same length as the original HTML), but hopefully it communicates the powerful idea behind includes.*

### Relative includes

We don’t have to put our includes into the `_includes` folder if we use the `include_relative` function instead. This function will look inside the same folder as the current file for the include to insert. It works really great for concatenating CSS files together.

```
---
---

{% raw %}{% include_relative header.css %}
{% include_relative footer.css %}
{% include_relative nav.css %}
{% include_relative cards.css %}{% endraw %}
```

This could be a `main.css` file that includes all the other smaller files to make our website more performant.

---

## Posts

Jekyll supports posts, like blog posts, that can be used as an ordered type of content.

Posts must be named very strictly and stored inside the `_posts` folder:

```
_posts/
  2013-09-26-water-in-martian-dirt.md
  2013-10-06-clouds-on-kepler-7b-mapped.md
  2013-10-09-planet-without-star.md
```

**The post’s file name must begin with a properly formatted date, in the format: `YYYY-MM-DD`.**

To display a list of posts in your website, you can use Jekyll’s loop:

```html
{% raw %}<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{site.baseurl}}{{post.url}}">{{post.title}}</a>
      <p>{{post.excerpt}}</p>
    </li>
  {% endfor %}
</ul>{% endraw %}
```

**Links**

- [Jekyll Docs: Posts](http://jekyllrb.com/docs/posts/)

---

## Collections

Collections are a mechanism in Jekyll that allow us to have a grouping of documents. The grouping can either act like datafiles or can act like pages and posts. **In fact, posts are just built-in collections.**

### Set up a collection in _config.yml

The first thing we need to do is create a collection in `_config.yml`, telling Jekyll how to handle it.

```yaml
collection:
  comets:
    output: true
    permalink: /comets/:path/
```

- The `collection` entry tells Jekyll we’re including new collections.
- The `comets` entry is the name of our collection—we completely make it up.
- The `output` entry is optional, here we’re telling Jekyll to turn the collection files into pages we can navigate to.
  <br>Without `output` the collection wouldn’t be navigable but could be pulled onto other pages like datafiles.
- The `permalink` entry tells Jekyll how to generate the URL for the collection pages.

### Outputting collection documents

In a page on our website we can loop through all the documents of a collection to generate some HTML.

```html
{% raw %}{% for comet in site.comets %}
  <h2>{{comet.title}}</h2>
  {{comet.content | markdownify}}
{% endfor %}{% endraw %}
```

### Collection pages

If the collection is set to output we can add layouts and everything else we’re used to doing with regular pages.

---

## Video list

1. [Jekyll: Installation](https://videos.learntheweb.courses/playlists/jekyll/#1-installation)
2. [Jekyll: Installation on older MacOS](https://videos.learntheweb.courses/playlists/jekyll/#2-installation-older-mac-os)
3. [Jekyll: Setting up on GitHub](https://videos.learntheweb.courses/playlists/jekyll/#3-gh-pages)
4. [Jekyll: Setting up a Jekyll project](https://videos.learntheweb.courses/playlists/jekyll/#4-setup-project)
5. [Jekyll: Starting and stopping](https://videos.learntheweb.courses/playlists/jekyll/#5-jekyll-start-stop)
6. [Jekyll: The _site folder](https://videos.learntheweb.courses/playlists/jekyll/#6-site-folder)
7. [Jekyll: Layouts](https://videos.learntheweb.courses/playlists/jekyll/#7-layouts)
8. [Jekyll: Creating navigation](https://videos.learntheweb.courses/playlists/jekyll/#8-navigation)
9. [Jekyll: Site baseurl](https://videos.learntheweb.courses/playlists/jekyll/#9-site-baseurl)
10. [Jekyll: Includes](https://videos.learntheweb.courses/playlists/jekyll/#10-includes)
11. [Jekyll: Adding CSS](https://videos.learntheweb.courses/playlists/jekyll/#11-adding-css)
12. [Jekyll: Highlighting navigation](https://videos.learntheweb.courses/playlists/jekyll/#12-highlight-nav)
13. [Jekyll: Include parameters](https://videos.learntheweb.courses/playlists/jekyll/#13-include-parameters)
14. [Jekyll: Looping over posts](https://videos.learntheweb.courses/playlists/jekyll/#14-posts-loop)
15. [Jekyll: Post categories](https://videos.learntheweb.courses/playlists/jekyll/#15-post-categories)
16. [Jekyll: Limiting the post loop](https://videos.learntheweb.courses/playlists/jekyll/#16-post-loop-limit)
17. [Jekyll: Nested layouts](https://videos.learntheweb.courses/playlists/jekyll/#17-nested-layouts)
18. [Jekyll: Highlighting navigation on multiple pages](https://videos.learntheweb.courses/playlists/jekyll/#18-nav-highlight-multi-page)
19. [Jekyll: Nested layouts for a specific content type](https://videos.learntheweb.courses/playlists/jekyll/#19-layout-for-content-type)
20. [Jekyll: Using posts for ordered content](https://videos.learntheweb.courses/playlists/jekyll/#20-post-hacked-for-content-order)
21. [Jekyll: Data files](https://videos.learntheweb.courses/playlists/jekyll/#21-data)
22. [Jekyll: Putting pages inside folders](https://videos.learntheweb.courses/playlists/jekyll/#22-pages-inside-folders)
23. [Jekyll: Looping over pages](https://videos.learntheweb.courses/playlists/jekyll/#23-pages-loop)
24. [Jekyll: Includes with page loops](https://videos.learntheweb.courses/playlists/jekyll/#24-page-loop-includes)
25. [Jekyll: Page loops and images](https://videos.learntheweb.courses/playlists/jekyll/#25-page-loop-images)
26. [Jekyll: Advanced nested layouts for specific content types](https://videos.learntheweb.courses/playlists/jekyll/#26-page-specific-layouts)
27. [Jekyll: Page sub-folders](https://videos.learntheweb.courses/playlists/jekyll/#27-page-sub-folders)
28. [Jekyll: Generating page navigation](https://videos.learntheweb.courses/playlists/jekyll/#28-page-navigation)
29. [Jekyll: Changing background images](https://videos.learntheweb.courses/playlists/jekyll/#29-css-changing-bg-images)
30. [Jekyll: Many CSS files](https://videos.learntheweb.courses/playlists/jekyll/#30-css-many-files)
31. [Jekyll: Relative includes](https://videos.learntheweb.courses/playlists/jekyll/#31-include-relative)
32. [Jekyll: Unique titles for every page](https://videos.learntheweb.courses/playlists/jekyll/#32-seo-unique-titles)
33. [Jekyll: Meta description](https://videos.learntheweb.courses/playlists/jekyll/#33-seo-meta-description)
34. [Jekyll: Automatic sitemap.xml](https://videos.learntheweb.courses/playlists/jekyll/#34-seo-sitemap)
35. [Jekyll: Pretty URLs](https://videos.learntheweb.courses/playlists/jekyll/#35-seo-pretty-urls)
36. [Jekyll: Creating a collection](https://videos.learntheweb.courses/playlists/jekyll/#36-collection)
37. [Jekyll: Extra collection info](https://videos.learntheweb.courses/playlists/jekyll/#37-collection-info)
38. [Jekyll: Collection index list](https://videos.learntheweb.courses/playlists/jekyll/#38-collection-index)
39. [Jekyll: Collection in sitemap.xml](https://videos.learntheweb.courses/playlists/jekyll/#39-collection-sitemap)

## Supplemental links

- [Jekyll Documentation](http://jekyllrb.com/)
- [Jekyll Setting Up on GitHub Pages](http://jekyllrb.com/docs/github-pages/)
- [**Awesome Jekyll Plugins**](https://github.com/planetjekyll/awesome-jekyll-plugins)
- [Shopify: Liquid for Designers](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers)
- [Shopify: Liquid Basics](http://docs.shopify.com/themes/liquid-basics)
- [CloudCannon Jekyll Cheat Sheet](https://learn.cloudcannon.com/jekyll-cheat-sheet/)
- [Jekyll by Example](http://www.andrewmunsell.com/tutorials/jekyll-by-example/)
- [GitHub Pages plugin list](https://help.github.com/articles/using-jekyll-plugins-with-github-pages/)
- [GitHub Pages versions](https://pages.github.com/versions/)
- [Jekyll Talk](https://talk.jekyllrb.com/)
- [Jekyll Tips](http://jekyll.tips/)
