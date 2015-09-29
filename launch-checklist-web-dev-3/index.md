---
layout: checklist
group: web-dev-3

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
    full: forms-checklist
    items:
      - 'All forms function properly.'
      - 'Forms have proper input types.'
      - 'All forms have a submit button.'
      - 'Forms have a proper completion message.'

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
      - 'Tested with keyboard only.'

  - title: 'Code quality'
    items:
      - 'All files follow naming conventions.<br>[Naming conventions](/topics/naming-paths-cheat-sheet/)'
      - 'All code is indented appropriately.<br>[HTML indentation](/topics/html-indentation/), [CSS indentation](/topics/css-indentation)'
      - 'HTML is valid.<br>[W3C HTML Validator](http://validator.w3.org/)'
      - 'CSS is valid.<br>[W3C CSS Validator](http://jigsaw.w3.org/css-validator/), [CSS Lint](http://csslint.net/)'
      - 'Validated for internationalization & world readiness.<br>[W3C Internationalization Checker](https://validator.w3.org/i18n-checker/)'
      - 'Many and high quality commit messages.'

  - title: 'Browser testing'
    full: browser-testing-checklist
    items:
      - 'All major touch points have been user tested.'
      - 'Tested in many desktop browsers.'
      - 'Tested on different devices including phones, tablets, laptops, desktops, and televisions.'
      - 'Tested on screen sizes ranging from 240px to ~2500px.'
      - 'Tested in low-bandwidth situations.'
      - 'Tested with common ad blockers.'

  - title: 'Details'
    items:
      - 'Has all the favicons.<br>[Favicons](/topics/image-formats/#favicons)'
      - 'Print styles are included.<br>[Print styles](/topics/media-queries/#print-styles)'

  - title: 'Performance'
    full: performance-checklist
    items:
      - 'Conforms to your performance budget.'
      - 'Code is organized for highest performance.'
      - 'All images have been properly sized, compressed, and smushed.'
      - 'Gets a high grade—or green light—in web performance tests.'
      - 'Redundant HTML, CSS, & Javascript have been removed.'

  - title: 'Javascript'
    full: javascript-checklist
    items:
      - 'All Javascript is in external files.'
      - 'All appropriate semicolons are in place.'
      - 'All user interactions have been thoroughly tested.'
      - 'Javascript has been validated.<br>[JS Hint](http://www.jshint.com/), [ESLint](http://eslint.org/), [JS Lint](http://jslint.com/)'
      - 'All instances of `console.log()` have been removed.'
      - 'Javascript has been tested for browser bugs.'
      - 'Appropriate accessibility features have been added.'

---
