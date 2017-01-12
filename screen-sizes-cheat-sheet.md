---
layout: cheatsheet
title: "Screen sizes cheat sheet"
tags: "screen sizes width media queries em responsive web design cheat sheet"
desc: "A cheat sheet with details on screen dimensions, common sizes, and testing."

groups:
  - title: 'The many sizes of the Web'
    items:
      - name: '![](screen-sizes.png)'
      - details:
          - '*Small sample of the many screen sizes.*'
          - 'Ranging in size from 320 × 240 – 5120 × 2880 (5K).'
          - 'It’s easier to simplify the sizes into classifications.'
      - details:
          - '*Remember: there is no fold on the Web.*'
          - '[LukeW: There is no fold](http://www.lukew.com/ff/entry.asp?1946)'

  - title: 'Size classifications'
    items:
      - name: '*Extra small* (320)'
        details:
          - '**(240px) 320px – 400px**'
          - 'Media query: *none—above the media queries*'
          - 'Font-size: `100%` (16px)'
          - 'Line-height: `1.3` (130%)'
          - 'Bottom margins: `1.3rem` (`<h1>`, `<p>`, `<ul>`, etc.)'
          - '&nbsp;'
          - |
            ```css
            html {
              font: normal 100%/1.3 sans-serif;
            }

            /*
              Add to anything that needs a bottom margin,
              for nice, cohesive vertical rhythm
            */
            h1,
            p {
              margin: 0 0 1.3rem;
            }
            ```
      - name: '*Small* (400)'
        details:
          - '**400px – 608px**'
          - 'Media query: `25em`'
          - 'Font-size: `100%` (16px)'
          - 'Line-height: `1.3` (130%)'
          - 'Bottom margins: `1.3rem`'
          - '&nbsp;'
          - |
            ```css
            @media only screen and (min-width: 25em) {

              html {
                font-size: 100%;
                line-height: 1.3;
              }

              h1,
              p {
                margin: 0 0 1.3rem;
              }

            }
            ```
      - name: '*Medium* (608)'
        details:
          - '**608px – 960px**'
          - 'Media query: `38em`'
          - 'Font-size: `110%` (17px)'
          - 'Line-height: `1.4` (140%)'
          - 'Bottom margins: `1.4rem`'
          - '&nbsp;'
          - |
            ```css
            @media only screen and (min-width: 38em) {

              html {
                font-size: 110%;
                line-height: 1.4;
              }

              h1,
              p {
                margin: 0 0 1.4rem;
              }

            }
            ```
      - name: '*Large* (960)'
        details:
          - '**960px – 1440px**'
          - 'Media query: `60em`'
          - 'Font-size: `120%` (19px)'
          - 'Line-height: `1.5` (150%)'
          - 'Bottom margins: `1.5rem`'
          - '&nbsp;'
          - |
            ```css
            @media only screen and (min-width: 60em) {

              html {
                font-size: 120%;
                line-height: 1.5;
              }

              h1,
              p {
                margin: 0 0 1.5rem;
              }

            }
            ```
      - name: '*Extra large* (1440)'
        details:
          - '**1440px+**'
          - 'Media query: `90em`'
          - 'Font-size: `130%` (20px)'
          - 'Line-height: `1.5` (150%)'
          - '&nbsp;'
          - |
            ```css
            @media only screen and (min-width: 90em) {

              html {
                font-size: 130%;
              }

            }
            ```
---
