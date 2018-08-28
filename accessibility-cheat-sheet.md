---
title: "Accessibility cheat sheet"
tags: "accessibility humans impairments universal design wai-aria landmark roles cheat sheet"
desc: "A cheat sheet covering the basic accessibility related code for websites."
layout: cheatsheet

related:
  - title: "Accessibility checklist"
    url: accessibility-checklist

groups:
  - title: 'Impairments overview'
    items:
      - name: '**Visual**'
        details:
          - 'Allow text to be resized.'
          - 'Have good contrast in colours.'
          - 'Test for colour blindness related issues.'
          - 'Make sure the website works well with screen readers.'
          - 'Use proper alt attributes.'
          - 'Don’t autoplay any sound.'
      - name: '**Mobility and dexterity**'
        details:
          - 'Recognize and prepare for the fact that not everybody will use a mouse.'
          - 'Make the website keyboard accessible.'
          - 'Increase hit areas of links and buttons.'
      - name: '**Cognitive**'
        details:
          - 'Make it clear where in the website the user is.'
          - 'Organize your content correctly & use proper headings.'
          - 'Make the text easily scannable.'
          - 'Clearly mark links.'
          - 'Use lots of images and graphics.'
          - 'Don’t autoplay any sound.'
      - name: '**Auditory**'
        details:
          - 'Provide text captions and subtitles.'
          - 'Don’t rely on sound for indicators.'
          - 'Don’t autoplay any sound.'

  - title: 'HTML semantics'
    items:
      - name: '**Table headers**'
        details:
          - 'The `<th>` tags should always denote which direction they label with the `scope` attribute.'
          - |
            ```html
            <th scope="col">…</th>
            <th scope="row">…</th>
            ```
      - name: '**Table captions**'
        details:
          - 'Tables should always include a description of the contents of the table for people who cannot see the tabular data.'
          - |
            ```html
            <table>
              <caption>Data describing the properties of many mystical creatures.</caption>
              ⋮
            </table>
            ```
      - name: '**Form labels**'
        details:
          - 'Every single form input must have an associated `<label>`'
          - |
            ```html
            <label for="mystical">Favourite mystical creature</label>
            <select id="mystical">
              <option>Unicorn</option>
            ⋮
            ```
          - '**The `placeholder` attribute is not an acceptable substitute.**'
      - name: '**Focus styles**'
        details:
          - 'Make is visually apparent what link is currently active.'
          - |
            ```css
            a:focus {
              outline: 3px solid #000;
            }
            ```
      - name: '**Skip links**'
        details:
          - 'Allow keyboard users to jump to specific locations on the page.'
          - |
            ```html
            <a href="#main">Jump to main content</a>

            ⋮

            <main role="main" id="main" tabindex="0">
            ```
          - '&nbsp;'
          - |
            ```css
            .skip-links a {
              position: absolute;
              top: -3em;
            }

            .skip-links a:focus {
              top: 0;
            }
            ```
      - name: '**SVG information**'
        details:
          - 'Add non-visible, descriptive information to SVGs inside HTML with the `<title>` and `<description>`'
          - |
            ```html
            <svg width="256" height="256" viewBox="0 0 256 256">
              <title>Unicorn leaping a rainbow</title>
              <description>A majestic white unicorn, with pink horn, leaping over a double rainbow.</description>
            </svg>
            ```

  - title: 'WAI-ARIA landmark roles'
    notes: 'All content should be within ARIA landmark roles. Roles should not be repeated on a single page.'
    items:
      - name: '`banner`'
        details:
          - 'Should be applied to the `<header>` tag'
          - |
            ```html
            <header role="banner">
              ⋮
            </header>
            ```
      - name: '`navigation`'
        details:
          - 'Should be applied to the `<nav>` tag'
          - |
            ```html
            <nav role="navigation">
              ⋮
            </nav>
            ```
      - name: '`main`'
        details:
          - 'Should be applied to the `<main>` tag'
          - |
            ```html
            <main role="main">
              ⋮
            </main>
            ```
      - name: '`contentinfo`'
        details:
          - 'Should be applied to the `<footer>` tag'
          - |
            ```html
            <footer role="contentinfo">
              ⋮
            </footer>
            ```
      - name: '`search`'
        details:
          - 'Should be applied to the `<form>` tag'
          - |
            ```html
            <form role="search">
              ⋮
            </form>
            ```
      - name: '`complementary`'
        details:
          - 'Should be applied to the `<aside>` tag'
          - |
            ```html
            <aside role="complementary">
              ⋮
            </aside>
            ```

  - title: 'Extra information'
    items:
      - name: '`aria-label`'
        details:
          - 'Assign non-visible text to enhance the description of an element.'
          - 'Can be used on any element to add more description.'
          - |
            ```html
            <a href="…" aria-label="Read more about of Mystical Animals">Read more</a>
            <h2 aria-label="Unicorns seen during ancient times">Unicorns</h2>
            ````
          - 'Also consider `aria-labelledby` to point to another element that holds the label text.'
      - name: '`aria-details`'
        details:
          - 'Assign the description of an element to other elements on the page.'
          - |
            ```html
            <img aria-details="#infographic-desc" src="big-complex-infographic.jpg" alt="">

            <div id="infographic-desc">
              <h2>All about unicorns</h2>
              <h3>Horns</h3>
              <ul>
                <li>…</li>
                ⋮
            </div>
            ```
      - name: '`role="presentation"`'
        details:
          - 'Force the browser to ignore the element because it’s not necessary for understanding the content.'
          - 'Good for hiding images that are purely decoration.'
          - |
            ```html
            <img src="…" alt="" role="presentation">
            ```
      - name: '`aria-hidden="true"`'
        details:
          - 'Force the browser to completely ignore an element from the accessibility tree.'
          - 'Usually paired with the `hidden` attribute.'
          - |
            ```html
            <div aria-hidden="true" hidden>
              ⋮
            </div>
            ```

---
