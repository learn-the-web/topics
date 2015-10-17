---
layout: cheatsheet
group: web-dev-4

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
          - '*Start Jekyll*'
          - |
            ```
            jekyll serve --watch --baseurl=""
            ```
          - '*View your website in a browser*'
          - |
            ```
            http://127.0.0.1:4000/
            ```
          - '*Stop Jekyll*'
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
          - '*Sample folder setup*'
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
          - ''
      - name: '*Page variables*'
        details:
          - ''
      - name: '*Nested layouts*'
        details:
          - ''
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
          - ''
      - name: '*Includes*'
        details:
          - ''
      - name: '*Posts*'
        details:
          - ''

  - title: 'Template tags'
    note: 'Check out the complete [Liquid for Designers](https://github.com/shopify/liquid/wiki/Liquid-for-Designers) resource.'
    items:
      - name: '*Output*'
        details:
          - ''
      - name: '*For*'
        details:
          - ''
      - name: '*If*'
        details:
          - ''

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
