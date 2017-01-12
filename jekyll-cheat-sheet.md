---
layout: cheatsheet
title: "Jekyll cheat sheet"
tags: "jekyll terminal layouts templates cheat sheet"
desc: "A cheat sheet covering the basics of Jekyll use and code."

groups:
  - title: 'Setup and use'
    items:
      - name: '*Installation*'
        details:
          - 'All these commands should be executed in Terminal, one-by-one, in order.'
          - |
            ```
            xcode-select --install
            ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
            brew install ruby
            gem install jekyll
            ```
          - '[**☛ Jekyll installation.**](/topics/jekyll-installation/)'
      - name: '*Starting & stopping*'
        details:
          - 'First, open your Jekyll folder in Terminal using the GitHub app shortcut—`⌘T`'
          - '*Start Jekyll:*'
          - |
            ```
            jekyll serve --watch --baseurl=""
            ```
          - '*View your website in a browser:*'
          - |
            ```
            http://127.0.0.1:4000/
            ```
          - '*Stop Jekyll:*'
          - |
            ```
            Control + C
            Or just quit Terminal.
            ```
          - '[**☛ Jekyll terminal guide.**](/topics/jekyll-terminal-guide/)'
      - name: '*Setting up Jekyll*'
        details:
          - 'Inside your folder you need to create the `_config.yml` file.'
          - |
            ```yaml
            permalink: pretty
            baseurl: /your-folder-on-github
            ```
          - '*Sample folder setup:*'
          - |
            ```
            _config.yml
            _data/
              └ dinos.yml
            _includes/
              └ button.html
            _layouts/
              └ default.html
            _posts/
              └ 2015-10-28-new-dino.md
              └ 2015-10-25-dinos-have-feathers.md
            css/
              └ main.css
            images/
              └ trex.jpg
            index.html
            meat-eaters.html
            ```

  - title: 'Files & paths'
    items:
      - name: '*Linking pages*'
        details:
          - 'With `permalink: pretty` turned on the `.html` extension can be left off URLs—but `{{site.baseurl}}` should be added.'
          - |
            ```html
            <a href="{{site.baseurl}}/plant-eaters/">Plant eaters</a>
            ```
      - name: '*Connecting CSS*'
        details:
          - 'Link CSS files like normal, except make sure to add `{{site.baseurl}}`'
          - |
            ```html
            <link href="{{site.baseurl}}/css/main.css" rel="stylesheet">
            ```
      - name: '*Linking images*'
        details:
          - 'Link images like normal, except make sure to add `{{site.baseurl}}`'
          - |
            ```html
            <img src="{{site.baseurl}}/images/trex.jpg" alt="">
            ```

  - title: 'Layouts'
    items:
      - name: '*Common header & footer*'
        details:
          - 'First create a new file inside the `_layouts` folder, name it whatever you want. Inside that file put the common HTML.'
          - '**Use `{{content}}` as the placeholder for the HTML from each page.**'
          - |
            ```html
            <!-- _layouts/default.html -->

            <!DOCTYPE html>
            <html lang="en-ca">
            <head>
              <meta charset="utf-8">
              <title></title>
            </head>
            <body>
              {{content}}
            </body>
            </html>
            ```
          - 'At the top of each page use YAML front matter to denote which layout to use:'
          - |
            ```html
            <!-- index.html -->

            ---
            layout: default
            ---

            <h1>Homepage</h1>
            ```
          - 'Layouts can be nested by including a different `layout` at the top of a layout HTML file.'
      - name: '*Page variables*'
        details:
          - 'To pass information from a page to a layout you can use YAML frontmatter.'
          - |
            ```html
            <!-- index.html -->

            ---
            layout: default
            title: Plant Eaters
            ---
            ```
          - 'Then inside the layout, we can use placeholder variables:'
          - |
            ```html
            <!-- _layouts/default.html -->

            <!DOCTYPE html>
            <html lang="en-ca">
            <head>
              <meta charset="utf-8">
              <title>{{page.title}}</title>
            ⋮
            ```
          - '[See the complete list of already included Jekyll page variables.](http://jekyllrb.com/docs/variables/)'
      - name: '*Highlighting navigation*'
        details:
          - 'Use an if-statement inside the `<a>` tag to add the `.current` class.'
          - |
            ```html
            <a href="{{site.baseurl}}/plant-eaters/" {% if page.url == '/plant-eaters/' %} class="current" {% endif %}>Plant eaters</a>
            ```

  - title: 'Data, includes & posts'
    items:
      - name: '*Data*'
        details:
          - 'Data files allow us to separate content from it’s presentation HTML.'
          - '*Put data files in the `_data` folder.*'
          - '**All the data is found in the variable `site.data`**'
          - |
            ```yaml
            # _data/dinos.yml

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
      - name: '*Includes*'
        details:
          - 'Includes are for making reusable, repeatable HTML blocks.'
          - '*Put includes int the `_includes` folder.*'
          - |
            ```html
            <!-- _includes/button.html -->

            <a class="btn" href="/go/">Go!</a>
            ```
          - |
            ```html
            {% include button.html %}
            {% include button.html %}
            ```
          - '*Pass information into includes:*'
          - |
            ```html
            {% include button.html url="/plant-eaters/" title="Plant eaters" %}
            ```
          - |
            ```html
            <!-- _includes/button.html -->

            <a class="btn" href="{{include.url}}">{{include.title}}</a>
            ```
      - name: '*Posts*'
        details:
          - 'Posts are like blog posts or news articles—time based, ordered content.'
          - '*Posts must be inside the `_posts` folder.*'
          - 'Name posts in the following, strict format: `YYYY-MM-DD-file-name.md`'
          - '**All the data is found in the variable `site.posts`**'
          - |
            ```
            _posts/
              2013-09-26-water-in-martian-dirt.md
              2013-10-06-clouds-on-kepler-7b-mapped.md
              2013-10-09-planet-without-star.md
            ```
          - 'Use the `for` loop to output posts:'
          - |
            ```html
            <ul>
              {% for post in site.posts %}
                <li>
                  <a href="{{site.baseurl}}{{post.url}}">{{post.title}}</a>
                  <p>{{post.excerpt}}</p>
                </li>
              {% endfor %}
            </ul>
            ```

  - title: 'Template tags'
    note: 'Check out the complete [Liquid for Designers](https://github.com/shopify/liquid/wiki/Liquid-for-Designers) resource.'
    items:
      - name: '*Output*'
        details:
          - 'The double curly braces, like `{{ }}` is to output something—they can be used anywhere to write it into the HTML.'
          - |
            ```html
            {{site.time}}
            <a href="{{page.url}}">Plant eaters</a>
            <h1>{{site.data.dinos[0].name}}</h1>
            ```
      - name: '*For*'
        details:
          - 'The for-loop is used to run over a collection of information like data or posts.'
          - |
            ```html
            {% for dino in site.data.dinos %}
              <h2>{{dino.name}}</h2>
              <dl>
                <dt>Diet</dt>
                <dd>{{site.diet}}</dd>
                <dt>Size</dt>
                <dd>{{site.size}}</dd>
              </dl>
            {% endfor %}
            ```
      - name: '*If*'
        details:
          - 'The if-statement can be used to do different things based on certain conditions.'
          - |
            ```html
            {% if page.url == '/' %}
              <h1>Dinosaurs Rock!</h1>
            {% else %}
              <strong>Dinosaurs Rock</strong>
            {% endif %}
            ```

  - title: 'Template filters'
    note: 'Check out the complete [Liquid for Designers](https://github.com/shopify/liquid/wiki/Liquid-for-Designers) resource & [Jekyll’s filter docs](http://jekyllrb.com/docs/templates/).'
    items:
      - name: '*Date*'
        details:
          - 'Will convert an ISO 8601 formatted date into something more friendly.'
          - |
            ```
            {{site.time | date: '%B %-d, %Y' }}
            ```
      - name: '*Replace*'
        details:
          - 'Will search for all instances of a piece of text and replace it with something else.'
          - |
            ```
            {{site.data.dinos[0].diet | replace: 'Meat', 'Plants' }}
            ```
      - name: '*Sort*'
        details:
          - 'Will sort a YAML object by a specific field.'
          - |
            ```
            {{site.data.dinos | sort: 'name' }}
            ```
      - name: '*Markdownify*'
        details:
          - 'Takes Markdown inside YAML and converts it to HTML.'
          - |
            ```
            {{site.data.dinos[0].name | markdownify }}
            ```
      - name: '*Slugify*'
        details:
          - 'Convert text to valid classes.'
          - |
            ```
            {{site.data.dinos[0].name | classify }}
            ```
      - name: '*Jsonify*'
        details:
          - 'Will convert an object or array into JSON.'
          - |
            ```
            {{site.data.dinos | jsonify }}
            ```
---
