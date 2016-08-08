---
layout: checklist

groups:
  - title: 'Performance Budget'
    note: 'Just an example; discuss with your team for what’s best for you.'
    items:
      - 'Load time: **< 1s** (1000ms).'
      - 'Speed index: **< 800**.<br>[WebPageTest](http://www.webpagetest.org/)'
      - 'Page size: **800 KB** transfer size maximum.'
      - 'Requests: **15 requests** maximum.'
      - 'Pass: [Google Mobile Friendly Test](https://www.google.com/webmasters/tools/mobile-friendly/).'
      - '[Google Page Speed](https://developers.google.com/speed/pagespeed/insights/): achieve yellow on Mobile & green on Desktop.'


  - title: 'Validation'
    items:
      - '![](web-page-test.png)'
      - '![](mobile-friendly.png)'
      - '![](page-speed.png)'


  - title: 'Design & code'
    items:
      - 'Tested with a slow/unreliable Internet connection.'
      - 'Tested in many small screen browsers & devices.'
      - 'Achieves high grades in web performance tests.<br>[WebPageTest](http://www.webpagetest.org/), [Google Page Speed](https://developers.google.com/speed/pagespeed/insights/), [YSlow](http://yslow.org/).'
      - 'Passes [Google Mobile Friendly Test](https://www.google.com/webmasters/tools/mobile-friendly/).'
      - 'Conforms to your performance budget.'
      - 'Images aren’t bigger than they need to be.'
      - 'Unnecessary images have been removed.'
      - 'Images properly saved using “Save for Web” from Photoshop.'
      - 'Images are as optimized as they can be.'
      - 'All images smushed after saving them.<br>[ImageOptim](https://imageoptim.com/), [SVGO](https://github.com/svg/svgo-gui)'
      - 'As few font styles are used as possible.'
      - 'Font special features are used sparingly—no `text-rendering: optimizeLegibility`'
      - 'Redundant HTML has been removed: no divitus, no hidden content, etc.'
      - 'All broken links and resources are removed.'
      - 'Put CSS `<link>` tags at the top, inside `<head>`'
      - 'Duplicate and redundant CSS has been removed.'
---
