---
layout: cheatsheet
title: "Commit message cheat sheet"
tags: "github commit message spelling length grammar singular imperative verb cheat sheet"
desc: "A cheat sheet describing the best practices for Git commit messages."

groups:
  - title: "Best practices"
    items:
      - name: '*Minimum 3 words & 10 characters*'
        details:
          - 'At least a minimum of 3 words.'
          - 'A total minimum of 10 characters.'
          - 'e.g “Fix a bug” isn’t good enough: correct number of words, too few characters.'
      - name: '*Proper spelling & grammar*'
        details:
          - 'All words should be spelled in Canadian English.<br>(*Only the commit message itself matters—American `color` in your code is okay.*)'
          - 'Sentence should be grammatically correct.'
          - 'Commits should not end in periods (`.`)'
      - name: '*Must start with an imperative verb*'
        details:
          - 'Start with words like “Fix”, “Add”, “Change”, etc.'
          - 'It’s best to imagine that all your commit messages start with the phrase: **“This commit will…”**'
          - 'First letter must be uppercase.'

  - title: "Examples"
    note: "This commit will…"
    items:
      - name: '*Good examples*'
        details:
          - '“Fix a bug in the navigation”'
          - '“Add the footer to all the pages”'
          - '“Improve browser support”'
          - '“Darken the masthead colours”'
          - '“Change the title of the page”'
      - name: '*Bad examples*'
        details:
          - '“asdf”'
          - '“Chagnes”'
          - '“Commit changes”'
          - '“Fixes a bug in the CSS”'
          - '“Remove the last section.”'
      - name: '*Example imperative verbs*'
        details:
          - '“Fix”, “Change”, “Add”, “Remove”, “Test”, “Amend”, “Calculate”, “Correct”, “Finish”, “Disable”, “Darken”, “Lighten”, “Format”, “Extract”, “Improve”, “Implement”, “Push”'
---
