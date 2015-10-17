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
          - '[**☛ Jekyll installation**](/topics/jekyll-installation/)'
      - name: '*Starting & stopping*'
        details:
          - 'First, open your Jekyll folder in Terminal using the GitHub app shortcut—`⌘T`'
          - '*Start Jekyll*'
          - |
            ```
            jekyll serve --watch --baseurl=""
            ```
          - '*Stop Jekyll*'
          - |
            ```
            Control + C
            ```
          - 'Or just quit Terminal.'
          - '[**☛ Jekyll terminal guide**](/topics/jekyll-terminal-guide/)'
      - name: '*Setting up Jekyll*'
        details:
          - 'Inside your folder you need to create the `_config.yml` file.'
          - |
            ```yaml
            permalink: pretty
            baseurl: /your-folder-on-github
            ```

---
