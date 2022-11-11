---
layout: cheatsheet
title: "Naming & paths cheat sheet"
tags: "naming conventions paths folders directories cheat sheet"
desc: "A cheat sheet describing the naming conventions for files and folders & path structure."

groups:
  - title: Naming conventions
    items:
      - name: '`all lowercase`'
        details:
          - 'All files & folder must us only lowercase characters.'
          - 'This includes extensions, like `.jpg`, `.png`, etc.'
          - 'The only exceptions are `README.md`, `LICENSE` & `CNAME`.'
      - name: '`Nospaces`'
        details:
          - 'No spaces allowed anywhere in file & folder names.'
          - 'Be careful their are spaces hidden at the end, after the extension.'
          - 'Use a dash (`-`) to separate words.'
      - name: '`Only letters, numbers & dashes`'
        details:
          - 'Use dashes (`-`) to separate words, e.g. super-duper.html.'
          - 'The only exception is the dot (`.`) before extensions.'
          - 'Underscores (`_`) are also acceptable.'
      - name: '*Good examples*'
        details:
          - '`index.html` — all lowercase.'
          - '`t-rex.png` — no spaces, dashes separating words.'
          - '`dragon-1.jpg` — only letters, numbers & dashes.'
      - name: '*Bad examples*'
        details:
          - '`Index.html` — capital letters used.'
          - '`t rex.png` — space in filename.'
          - '`dragon’s egg.jpg` — apostrophe is a non-standard character.'
      - name: '*Be careful*'
        details:
          - '`dragon.JPG` — some programs like to use uppercase extensions—*change them to lowercase*.'
          - '`full-site.tar.gz` — multiple extensions are okay.'
          - '`_archive` — underscores are fine, but try to avoid them.'

  - title: 'Paths & folders'
    items:
      - name: '`./` or *nothing*'
        details:
          - 'Start in the same location.'
          - '`./about.html` or `about.html`'
      - name: '`../`'
        details:
          - 'Go out of a folder.'
          - 'Can be chained: `../../`.'
          - '`../index.html`'
      - name: '`/`'
        details:
          - 'Start at the root of the computer or the root of the domain.'
          - '`/index.html` or `/Dropbox/image.jpg`'
      - name: '`//`'
        details:
          - 'Start immediately after the protocol, replace the domain.'
          - '`//github.com`'
      - name: '`https://`'
        details:
          - 'Start at the top level of the Internet, replace everything.'
          - '`https://github.com`'
      - name: '`~/`'
        details:
          - 'Start in your home folder.'
          - '*Doesn’t work on the web.*'
          - '`~/Desktop/todo.txt`'
---
