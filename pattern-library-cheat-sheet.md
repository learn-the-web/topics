---
title: "Pattern library cheat sheet"
tags: "css style guides pattern library libraries templates themes tiles components modules systems mood boards cheat sheet"
desc: "A cheat sheet covering the important bits of building pattern libraries with Jekyll Patternbot."
layout: cheatsheet

related:
  - title: "Jekyll"
    url: jekyll
  - title: "Jekyll installation"
    url: jekyll-installation
  - title: "Jekyll terminal guide"
    url: jekyll-terminal-guide
  - title: "Jekyll cheat sheet"
    url: jekyll-cheat-sheet

groups:
  - title: 'Installation & setup'
    items:
      - name: '*Tool installation*'
        details:
        details:
          - 'All these commands should be executed in Terminal, one-by-one, in order.'
          - |
            ```
            xcode-select --install
            /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
            brew install ruby
            echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' >> ~/.bash_profile
            ```
          - 'Then open your repo in Terminal, from GitHub Desktop: `Repository > Open in Terminal`'
          - |
            ```
            bundle init
            ```
          - 'Open the new `Gemfile`, add the following line:'
          - |
            ```ruby
            gem "jekyll"

            group :jekyll_plugins do
              gem "jekyll_patternbot"
            end
            ```
          - 'Pop back to Terminal, type:'
          - |
            ```
            bundle install
            ```
      - name: '*Jekyll Patternbot & Netlify setup*'
        details:
          - 'Create a new file: `_config.yml`'
          - |
            ```yml
            permalink: pretty
            theme: jekyll_patternbot
            ```
          - 'Create a new file: `.ruby-version`'
          - '*Add a fairly current Ruby version number, like:*'
          - |
            ```
            2.6.2
            ```
          - '**Make sure everything’s committed.**'
          - 'Create an account on [Netlify](https://www.netlify.com/), using your GitHub account.'
          - 'Add a new site, and connect your repo.'
          - '“Build command”—`jekyll build`'
          - '“Publish directory”—`_site`'
          - '**Copy the link from Netlify & put it in your GitHub repo.**'
      - name: '*Starting & stopping*'
        details:
          - 'First, open your Jekyll folder in Terminal using the GitHub app shortcut—``⌃` ``'
          - '**Start Jekyll:**'
          - |
            ```
            bundle exec jekyll serve
            ```
          - '*View your website in a browser:*'
          - |
            ```
            http://localhost:4000/
            ```
          - '**Stop Jekyll:**'
          - |
            ```
            Control + C
            Or just quit Terminal.
            ```
          - '[**☛ Jekyll terminal guide.**](/topics/jekyll-terminal-guide/)'
          - 'If hosting on GitHub, don’t forget `baseurl`'
          - |
            ```
            bundle exec jekyll serve --baseurl=""
            ```

  - title: 'Folders & files'
    items:
      - name: '*Folder structure*'
        details:
          - 'Here’s a typical structure for a Patternbot folder.'
          - |
            ```
            _config.yml
            _layouts/
              └ default.html
            _patterns/
              └ buttons/
                 └ basic.html
                 └ ghost.html
                 └ buttons.css
                 └ config.yml
              └ banners/
                 └ call-to-action.html
                 └ carousel.html
                 └ banners.css
                 └ banners.js
                 └ config.yml
            css/
              └ modules.css
              └ grid.css
              └ type.css
              └ theme.css
              └ main.css
            images/
              └ icons.svg
              └ logo.svg
              └ logo-16.svg
            ```
      - name: '*CSS*'
        details:
          - 'Patternbot will do special things with your CSS files:'
          - |
            ```
            css/
              └ modules.css
              └ grid.css
              └ type.css
              └ theme.css
              └ main.css
            ```
          - '`modules.css` — will show different features & classes from [Modulifier](https://modulifier.web-dev.tools/).'
          - '`grid.css` — will show different sizes & classes from [Gridifier](https://gridifier.web-dev.tools/).'
          - '`type.css` — will show different sizes & classes from [Typografier](https://typografier.web-dev.tools/).'
          - '**`main.css`** — used to combine all the CSS together, like this:'
          - |
            ```css
            ---
            ---
            {% include_relative modules.css %}
            {% include_relative grid.css %}
            {% include_relative type.css %}
            {% include_relative theme.css %}
            {% pattern_css %}
            ```
      - name: '`theme.css`'
        details:
          - 'Patternbot parses variables from your `theme.css` file, inside the `:root` selector:'
          - '*Colours variables start with `--color-`*'
          - |
            ```css
            :root {
              --color-primary: red;
              --color-primary-dark: crimson;
              --color-secondary: green;
              --color-secondary-muted: olive;
              --color-neutral: #e2e2e2;
              --color-neutral-dark: rgb(40, 40, 40);
              --color-accent: hotpink;
              --color-awesome: cornsilk;
            }
            ```
          - '`--color-primary` is treated as the most important colour.'
          - '`--color-secondary` is treated as the second most important colour.'
          - '`--color-neutral` & `--color-accent` are grouped.'
          - '*Font variables start with `--font-`*'
          - |
            ```css
            :root {
              --font-primary: Georgia, serif;
              --font-secondary: "Sarabun", sans-serif;
              --font-accent: "Abril Fatface", serif;
            }
            ```
      - name: '*Logos*'
        details:
          - 'Patternbot will look for `.svg` and `.png` images in the `images/` folder'
          - |
            ```
            images/
              └ logo.svg
              └ logo-64.svg
              └ logo-32.svg
              └ logo-16.svg
            ```
      - name: '*Icons*'
        details:
          - 'Patternbot will look for `.svg` spritesheets in the `images/` folder'
          - |
            ```
            images/
              └ icons.svg
            ```
      - name: '*JS*'
        details:
          - 'Follows the same system as CSS:'
          - '**`main.js`** — used to combine all the JS together, like this:'
          - |
            ```css
            ---
            ---
            {% include_relative jquery.css %}
            {% include_relative font-helper.css %}
            {% pattern_js %}
            ```
      - name: '*Sample pages*'
        details:
          - 'Put HTML files into the `sample-pages` folder and they will show in Patternbot’s navigation.'
          - |
            ```
            sample-pages/
              └ home-page.html
              └ product-details.html
            ```
      - name: '*Utility classes*'
        details:
          - 'Write descriptions for classes within `theme.css` using the `@utility` tag to highlight them in Patternbot.'
          - |
            ```css
            /* @utility Set the type using the accent typeface */
            .font-accent {
              font-family: var(--font-accent);
            }

            /* @utility Add an appropriate border to the bottom of an element */
            .borderify {
              border-bottom: .1em solid var(--color-neutral);
            }
            ```
      - name: '*Utility variables*'
        details:
          - 'Describe & call out other variables within `:root` with the `@var` tag:'
          - |
            ```css
            :root {
              /* @var The standard border radius to be use whenever rounded corners are required */
              --border-radius: 8px;
              /* @var Use to add a semi-transparent background overlay */
              --bg-overlay: rgba(0, 0, 0, .5);
            }
            ```

  - title: 'Configuration & documentation'
    items:
      - name: '`_config.yml` settings'
        details:
          - 'Scope all of Patternbot’s settings under the `patternbot:` key:'
          - |
            ```yml
            patternbot:
              title: "Dino Rescue"
              description: |
                A small local dinosaur rescue organization specializing in herbivores. Dinos are in danger and we need to save them all!
              # Supports all online font systems that give CSS URLs
              font_url: "https://fonts.googleapis.com/css?family=Overpass:400,400i,700|Source+Code+Pro:400,700"

              # Define colours for the interface
              colors:
                background: "--color-neutral"
                accent: "--color-primary"
                patterns:
                  brand.logos: "--color-primary-dark"
                  grids.grid-sizes: "--color-secondary"
                  # Style the background colour of icons
                  icons.icons.micropachycephalosaurus: "--color-primary-light"
                  # Apply colours to SVG spritesheet variables
                  icons.icons.velociraptor.--color-stroke: "black"

              # Rationalize typeface & colour choices
              rationales:
                typefaces.primary: |
                    The primary typeface represents clarity and simplicity. It should be used for just about everything.
                typefaces.secondary: |
                    The secondary typeface is specifically for code samples within the website.
                colors.primary: |
                    Well it’s red because why not.
                colors.secondary: |
                    This colour was chosen because it’s complementary to red. It should be used sparingly for little punches of difference.

              # Explain when to use Jekyll layouts
              layouts:
                default: |
                  To be used for every page, contains the masthead and footer.
            ```
      - name: '*Pattern documentation*'
        details:
          - 'Add a `config.yml` to pattern folders for documentation.'
          - |
            ```yml
            title: "Buttons"
            description: |
              The buttons use our primary colour to draw attention and stand out. Each button has a specific purpose:
            patterns:
              # The key is the same as the HTML file’s name
              basic:
                title: "Basic"
                description: |
                  Things & stuff & junk.
              ghost:
                title: "Ghost"
            ```
      - name: '*Pattern configuration*'
        details:
          - 'Each pattern has a little bit of configuration for its display in Patternbot.'
          - |
            ```yml
            patterns:
              basic:
                # Change the background color of the pattern
                background: "--color-accent"
                # Set the initial width of the pattern’s display
                width: 400
                # Add padding around the pattern to help it display
                padding: 3em
                # Specify the Jekyll include fields
                fields:
                  # The name of the field for Jekyll
                  - name: 'url'
                    # The type of information the include expects
                    type: 'string'
                    # An example of what the content is
                    example: '/products'
                    # Specify if the information is optional
                    required: false
                  - name: 'class'
                    type: 'class'
                    # If the type is `class` specify what classes are acceptable
                    classes:
                      - 'btn-ghost'
                      - 'btn-subtle'
                  - name: "data"
                    type: "object"
                    # Send a Jekyll piece of data to populate the include’s information
                    data:
                      source: "site.data.products[1]"
                      type: "Product"
            ```

---
