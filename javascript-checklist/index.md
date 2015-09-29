---
layout: checklist
group: web-dev-3

groups:
  - title: 'Code quality'
    items:
      - 'All Javascript is in external files.'
      - 'The `<script>` tags are placed at the bottom of the HTML file.'
      - 'All appropriate semicolons are in place.'
      - 'All instances of `console.log()` have been removed.'
      - 'Appropriate accessibility features have been added.'
      - 'Code is properly indented and spaced.'
      - 'Code, spacing, brackets, etc. follows a consistent style.'
      - 'Only relevant and important comments still exist.'

  - title: 'Testing'
    items:
      - 'All user interactions have been thoroughly tested.'
      - 'All interactions tested with keyboard only.'
      - 'All interactions tested with a screen reader and other accessibility tools.'
      - 'Javascript has been tested in many browsers.'
      - 'Javascript has been tested on many screen sizes.'
      - 'Website has been tested with Javascript disabled.'
      - 'Tested in low-bandwidth situations.'

  - title: 'Validation'
    items:
      - 'Javascript has been validated.<br>[JS Hint](http://www.jshint.com/), [ESLint](http://eslint.org/), [JS Lint](http://jslint.com/)'
      - 'Automated & unit testing has been considered.'
      - 'Validated for internationalization & world readiness.<br>[W3C Internationalization Checker](https://validator.w3.org/i18n-checker/)'
      - 'Many and high quality commit messages.'

---
