---
layout: checklist
group: web-dev-2

groups:
  - title: 'Content'
    items:
      - 'Proper semantics are used for all content.<br>[HTML semantics](/topics/html-semantics/)'
      - 'Contents & HTML elements are in a logical order: most important at the top.'
      - 'Headings are ordered properly.'
      - 'Links pointing to different locations should have different text.'
      - 'The `<em>` and `<i>` tags are not used to make text italic.'
      - 'The `<strong>` and `<b>` tags are not used to make text bold.'
      - 'Tables are only used for tabular data.<br>[Tables](/topics/tables/)'
      - 'Table cells are associated with their headers using `scope`.'
      - 'All form elements have an associated label.<br>[Forms](/topics/forms/)'
      - 'All form error messages are visible and understandable.'
      - 'Language is defined on the HTML tag.'
      - 'The `<title>` is descriptive and informative.'
      - 'Provide meanings of unusual words and pronunciations of difficult words.'

  - title: 'Design'
    items:
      - 'No primary text is smaller than 16px.'
      - 'Elements appear in the same location on every page visually and code-wise.'
      - 'Colour is not used as the sole method of conveying information.'
      - 'Links are distinguished from surrounding text with more than colour.'
      - 'Colour contrast issues have been resolved.<br>[Color Oracle](http://colororacle.org/)'
      - 'Website is readable and functional with in a range font sizes: 2 bigger, 2 smaller.'
      - 'Line-length is not too long.'
      - 'Justified text isn’t used, or used extremely sparingly.'

  - title: 'Usability'
    items:
      - 'The current page & location are highlighted.<br>[Highlighting the current page](/topics/navigation/#highlighting-the-current-page)'
      - 'Focus styles for keyboard users work.<br>[Focus styles](/topics/accessibility#focus-styles)'
      - 'Hit areas, links & buttons, are big enough for thumbs and users with difficulty using the mouse.'
      - 'Properly implemented skip links.<br>[Skip links](/topics/accessibility#skip-links)'
      - 'Correct elements have WAI-ARIA landmark roles.<br>[Landmark roles](/topics/accessibility#wai-aria-roles)'
      - 'Appropriate elements have ARIA attributes.<br>[Javascript & accessibility](/topics/javascript-accessibility/)'
      - 'Animations can be stopped.'
      - 'No presentational elements are read by accessibility tools.'
      - 'Timed functionality can be controlled.'
      - 'Required & optional form elements are denoted.'

  - title: 'Images & media'
    items:
      - 'Images have appropriate alt attributes.<br>[Alt attributes](/topics/using-images/#alt-attributes)'
      - 'SVGs have titles & descriptions.<br>[SVG accessibility](/topics/advanced-svg/#embedded-svg-accessibility)'
      - 'No audio or video plays automatically.'
      - 'Audio files have written transcripts.'
      - 'Video files have captions or transcripts.'

  - title: 'Testing'
    items:
      - 'Tested with many users of different needs.'
      - 'Conforms to WCAG 2 AA or higher.<br>[AccessLint](http://www.accesslint.com/)'
      - 'Has been tested with screen readers.<br>[VoiceOver](/topics/accessibility#voice-over)'
      - 'Tested with images disabled.'
      - 'Tested with CSS disabled.'
      - 'Tested with keyboard only.'
      - 'Tested with a text-only browser.<br>[Lynx Viewer](http://www.clickability.co.uk/lynx-viewer.php)'

---
