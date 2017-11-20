---
layout: checklist
title: "Launch checklist"
tags: "launch checklist double check validators link checkers usability browser testing analytics monitoring"
desc: "A checklist of things to check on your website before you launch it, for Web Dev 4."

groups:
  - title: 'Content & usability'
    items:
      - 'All text is free from spelling and grammar errors.'
      - 'There’s no placeholder text or images on the website.'
      - 'Company logo links to the homepage.'
      - 'Content has semantically appropriate elements.<br>[HTML semantics](/topics/html-semantics/)'
      - 'Footer includes copyright information, terms, privacy policy, cookie notice, etc.'
      - 'All links work.<br>[W3C link checker](http://validator.w3.org/checklink), [Integrity](http://peacockmedia.co.uk/integrity/)'
      - 'All images display properly.'
      - 'All email addresses and phone numbers are linked.'

  - title: 'Design'
    items:
      - 'Content has been placed consistently.'
      - 'Navigation is consistently placed.'
      - 'Shared page elements don’t shift from page to page.'
      - 'Responsiveness works well on all screen sizes: no weird spacing issues, no overlapping text, etc.'
      - 'Follows good typography and graphic design conventions.'
      - 'Has consistent graphic design style and vision.'
      - 'All different page layouts have been tested.'

  - title: 'Forms'
    items:
      - 'All forms function properly, the `action` pointing to the proper location.'
      - 'Forms have proper input types.'
      - 'All forms have a submit button.'
      - 'Forms have a proper completion message.'
      - 'All inputs have an associated `<label>`.'
      - 'Placeholders are used as examples, not as labels.'
      - 'Groups of radio buttons and check boxes are organized in a `<fieldset>`'
      - 'At least one field is marked as `required`'
      - 'All unnecessary fields are removed from the form.'

  - title: 'Accessibility'
    full: accessibility-checklist
    items:
      - 'Images have appropriate alt attributes.'
      - 'Focus styles for keyboard users work.'
      - 'Correct elements have WAI-ARIA landmark roles.'
      - 'Properly implemented skip links.'
      - 'Colour contrast issues have been resolved.'
      - 'Conforms to WCAG 2 AA or higher.'
      - 'Appropriate elements have ARIA attributes.'
      - 'Has been tested with accessibility tools.'
      - 'Tested with many accessibility scenarios.'
      - 'All links stand out from content & have visible focus states.'
      - 'Hover isn’t the only method for accessing content.'

  - title: 'Code quality'
    items:
      - 'All files follow naming conventions.<br>[Naming conventions](/topics/naming-paths-cheat-sheet/)'
      - 'All code is indented appropriately.<br>[HTML indentation](/topics/html-indentation/), [CSS indentation](/topics/css-indentation)'
      - 'HTML is valid.<br>[W3C HTML Validator](http://validator.w3.org/)'
      - 'CSS is valid.<br>[W3C CSS Validator](http://jigsaw.w3.org/css-validator/), [CSS Lint](http://csslint.net/)'
      - 'Validated for internationalization & world readiness.<br>[W3C Internationalization Checker](https://validator.w3.org/i18n-checker/)'
      - 'Many and high quality commit messages.<br>[Commit message cheat sheet](http://localhost:4000/topics/commit-message-cheat-sheet/)'

  - title: 'Browser testing'
    full: browser-testing-checklist
    items:
      - 'All user interactions have been user tested.'
      - 'Tested in many desktop browsers.'
      - 'Tested on different devices including phones, tablets, laptops, desktops, and televisions.'
      - 'Tested on screen sizes ranging from 320px to ~2500px.'
      - 'Tested in low-bandwidth situations.'
      - 'Tested with common ad blockers.'

  - title: 'Details'
    items:
      - 'Has a 404 page.<br>[404 pages](/topics/404-pages/)'
      - 'Has all the favicons.<br>[Favicons](/topics/image-formats/#favicons)'
      - 'GitHub project has a complete Readme.<br>[Writing a readme](/topics/writing-a-readme/)'
      - 'Print styles are included.<br>[Print styles](/topics/media-queries/#print-styles)'

  - title: 'Performance'
    full: advanced-performance-checklist
    items:
      - 'Conforms to your performance budget.'
      - 'Code is organized for highest performance.'
      - 'All images have been properly sized, compressed, and smushed.'
      - 'Gets a high grade—or green light—in web performance tests.'
      - 'Redundant HTML, CSS, & JavaScript have been removed.'
      - 'CSS & JS have been concatenated & minified.'
      - 'Sends appropriate caching headers.'
      - 'Resources sent in a compressed format.'
      - 'Content served from a CDN.'

  - title: 'Search engine optimization'
    full: seo-checklist
    items:
      - 'Has been honestly search engine optimized.'
      - 'Every page has a unique, descriptive title.'
      - 'Every page has a unique meta description.'
      - 'Every page has an obvious goal.'
      - 'Has appropriate enhanced semantics.'
      - 'Has all the social media meta tags.'
      - 'Has a robots.txt and complete humans.txt.'
      - 'Has a sitemap.xml file.'
      - 'Registered in search engine tools.'
      - 'Analytics package is set up.'
      - 'Uptime monitoring package set up.'

---
