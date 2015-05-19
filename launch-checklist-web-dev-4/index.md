---
layout: checklist
group: web-dev-4

groups:
  - title: 'Content & usability'
    items:
      - 'All text is free from spelling and grammar errors.'
      - 'There’s no placeholder text or images on the website.'
      - 'Content has semantically appropriate elements.<br>[HTML semantics](/topics/html-semantics/)'
      - 'Footer includes copyright information, terms, privacy policy, cookie notice, etc.'
      - 'All links work.<br>[W3C link checker](http://validator.w3.org/checklink).'
      - 'All images display properly.'

  - title: 'Design'
    items:
      - 'Content has been placed consistently.'
      - 'Navigation is consistently placed.'
      - 'Shared page elements don’t shift from page to page.'
      - 'Responsiveness works well on all screen sizes: no weird spacing issues, no overlapping text, etc.'
      - 'Follows good typography and graphic design conventions.<br>[Modular typography](/topics/modular-typography), [Grids](/topics/grids).'
      - 'Has consistent graphic design style and vision.'

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
      - 'Images have appropriate alt attributes.<br>[Alt attributes](/topics/images#alt-attributes)'
      - 'Focus styles for keyboard users work.<br>[Focus styles](/topics/accessibility#focus-styles)'
      - 'Correct elements have WAI-ARIA landmark roles.<br>[Landmark roles](/topics/accessibility#wai-aria-roles)'
      - 'Properly implemented skip links.<br>[Skip links](/topics/accessibility#skip-links)'
      - 'Colour contrast issues have been resolved.<br>[Color Oracle](http://colororacle.org/)'
      - 'Conforms to WCAG 2 AA or higher.<br>[TotalValidator](http://www.totalvalidator.com/index.html)'

  - title: 'Code quality'
    items:
      - 'All files follow naming conventions.<br>[Naming conventions](/topics/naming-conventions.md)'
      - 'All code is indented appropriately.<br>[HTML indentation](/topics/html-indentation/), [CSS indentation](/topics/css-indentation)'
      - 'HTML is valid.<br>[W3C HTML Validator](http://validator.w3.org/)'
      - 'CSS is valid.<br>[W3C CSS Validator](http://jigsaw.w3.org/css-validator/), [CSS Lint](http://csslint.net/)'
      - 'Javascript has been validated.<br>[JS Hint](http://www.jshint.com/), [JS Lint](http://jslint.com/)'
      - 'Many and high quality commit messages.'

  - title: 'Testing'
    full: browser-testing-checklist
    items:
      - 'All major touch points have been user tested.'
      - 'Has been tested with accessibility tools.<br>[VoiceOver](/topics/accessibility#voice-over)'
      - 'Tested in many browsers including IE, FF, Safari, Chrome & Opera.'
      - 'Tested on screen sizes ranging from 240 px to ~2500 px.'
      - 'Tested on different devices including phones, tablets, laptops, desktops, and televisions.<br>[BrowserStack](http://www.browserstack.com/), [RemoteIE](https://remote.modern.ie/)'

  - title: 'Details'
    items:
      - 'Has a 404 page.<br>[404 pages](/topics/404-pages)'
      - 'Has all the favicons.<br>[Favicons](/topics/images#favicons)'
      - 'GitHub project has a complete Readme.'
      - 'Print stylesheet is included.'

  - title: 'Performance'
    full: advanced-performance-checklist
    items:
      - 'All images have been properly sized, compressed, and smushed.<br>[Compressing & smushing images](/topics/images#speed-of-images)'
      - 'Gets a high grade—or green light—in web performance tests.<br>[MobileOK](http://validator.w3.org/mobile/), [Google Page Speed](https://developers.google.com/speed/pagespeed/insights/), [YSlow](http://yslow.org/)'

  - title: 'Search engine optimization'
    full: seo-checklist
    items:
      - 'Has been honestly search engine optimized.<br>[Honest SEO](/topics/search-engine-optimization)'
      - 'Every page has a unique, descriptive title.<br>[Title formula](/topics/search-engine-optimization#page-title-formula)'
      - 'Every page has a unique meta description.<br>[Meta descriptions](/topics/search-engine-optimization#meta-descriptions)'
      - 'Every page has an obvious goal.'
      - 'Has appropriate enhanced semantics.<br>[Metadata](/topics/metadata-enhanced-semantics#structured-data), [Google Rich Snippets](http://www.google.com/webmasters/tools/richsnippets), [Schema.org](http://schema.org)'
      - 'Has all the social media meta tags.<br>[Social media tags](/topics/metadata-enhanced-semantics#social-semantics)'
      - 'Has a robots.txt and complete humans.txt.<br>[Robots.txt & humans.txt](/topics/search-engine-optimization#robots--humans)'
      - 'Has a sitemap.xml file.<br>[Sitemap.xml](/topics/search-engine-optimization#sitemaps)'
      - 'Registered in search engine tools.<br>[Google Webmaster Central](http://www.google.ca/webmasters/), [Bing Webmaster Tools](http://www.bing.com/toolbox/webmaster)'
      - 'Analytics package is set up.<br>[Google Analytics](http://www.google.com/analytics/?gclid=COC2_qf08MECFePyMgodb10AAQ)'
      - 'Uptime monitoring package set up.<br>[UptimeRobot](http://uptimerobot.com/), [Pingdom](https://www.pingdom.com/pricing/), [updown.io](https://updown.io/)'

---
