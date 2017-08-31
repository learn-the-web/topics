---
layout: checklist
title: "Troubleshooting checklist"
tags: "html css github validation debug troubleshooting bug problems fix help checklist"
desc: "A checklist for trying to solve and debug code and Web Dev related problems."

groups:
  - title: 'General'
    items:
      - 'Is it saved?'
      - 'Did you refresh it?'
      - 'Have you refreshed it multiple times?'
      - 'Is it committed in the GitHub app?'
      - 'Is it pushed/synced in the GitHub app?'
      - 'Did you wait a few minutes for the server to sync your live website?'
      - 'Are you editing the correct file in Atom? `⌘-Click` the filename in the window’s title bar.'
      - 'Are you viewing the correct file in your browser? Check the URL folders against the folder structure on your computer.'
      - 'Is the file in the trash? `⌘-Click` the title bar or check the URL.'
      - 'Are you connected to the Internet?'
      - 'Have you restarted Atom? Fully `⌘Q` restart.'
      - 'Have you restarted the browser? Fully `⌘Q` restart.'
      - 'Have you asked your neighbour?'
      - 'Have you asked a TA (yellow sticky)?'
      - 'Have you asked the Teacher (red sticky)?'
      - 'Is it time for a break?'
      - 'Have you slept on it? Wait until you start dreaming solutions.'
      - 'Have you restarted your computer?'
      - 'Did you give the computer gnomes enough time to fix it for you?'

  - title: 'HTML'
    items:
      - 'Have you validated the code?<br>[HTML Validator](https://validator.w3.org/) or Markbot'
      - 'Is the tag name spelled properly?'
      - 'Are the attributes spelled properly?'
      - 'Is it indented properly? (Helps with understanding.)'
      - 'Are all the tags closed properly?'
      - 'Is there a `"` missing?'
      - 'Are there `<` or `>` characters missing?'
      - 'Have you run it through Markbot?'
      - 'Is the CSS file connected using a `<link>` tag?'
      - 'Is the path to the CSS file correct?'
      - 'Is the CSS file saved in a `css` folder that’s the same location as your `index.html`?'
      - 'Does the image’s `src` attribute point to the right folder and file?'

  - title: 'CSS'
    items:
      - 'Have you validated the code?<br>[CSS Validator](https://jigsaw.w3.org/css-validator/) or Markbot'
      - 'Are the properties & values spelled properly?'
      - 'Is it indented properly? (Helps with understanding.)'
      - 'Do all the lines have a closing `;`?'
      - 'Are there any missing `{` or `}` at the start or end of a ruleset?'
      - 'Are there enough closing `}` after a media query? There should be 2.'
      - 'Is there a quote missing?'
      - 'Are there any missing `,` between selectors?'
      - 'Have you run it through Markbot?'
      - 'Is the class spelled properly?'
      - 'Does the class’s name start with a `.`?'
      - 'Does the selector you’ve used actually exist in the HTML?'
      - 'Did you spell `color` the American way?'
      - 'Are you using a class when it’s actually an ID in your HTML?'

  - title: 'GitHub'
    items:
      - 'Have you committed everything?'
      - 'Have you pushed/synced everything?'
      - 'Have you waited ~10 minutes for it to become live online?'
      - 'Are you signed into the GitHub app? Check `Preferences > Accounts`'
      - 'Have you tried signing out then signing back in again?'
      - 'Have you verified your email address? Check the website.'
      - 'Is your email address saved in the preferences? Check `Preferences > Git`'
      - 'Are you viewing the right folder? Go to `Repository > Show in Finder`'
      - 'Is the Git repo in the trash? Go to `Repository > Show in Finder`'
      - 'Did you fork the original assignment repo? Go to `Repository > Repository Settings…`; is the Algonquin Web Dev username (acgd-webdev-*) in the “Remote” URL?'
      - 'Did you submit your GitHub username at the start of the year for the grade submission to work? Ask [Thomas](mailto:thomas.bradley@algonquincollege.com) for confirmation.'
---
