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
          - ''
      - name: '*Connecting CSS*'
        details:
          - ''
      - name: '*Linking images*'
        details:
          - ''

  - title: 'Layouts'
    items:
      - name: '*Linking pages*'
        details:
          - ''

  - title: 'Data'
    items:
      - name: '*Linking pages*'
        details:
          - ''

  - title: 'Includes'
    items:
      - name: '*Linking pages*'
        details:
          - ''

  - title: 'Posts'
    items:
      - name: '*Linking pages*'
        details:
          - ''

  - title: 'Template tags'
    items:
      - name: '*Linking pages*'
        details:
          - ''

  - title: 'Template filters'
    items:
      - name: '*Linking pages*'
        details:
          - ''
---
