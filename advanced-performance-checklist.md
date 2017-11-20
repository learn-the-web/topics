---
layout: checklist
title: "Advanced performance checklist"
tags: "performance speed download checklist"
desc: "A checklist for website performance validation."

groups:
  - title: 'Performance Budget'
    note: 'Just an example; discuss with your team for what’s best for you.'
    items:
      - 'Load time: **< 1s** (1000ms).'
      - 'Speed index: **< 800**.<br>[WebPageTest](http://www.webpagetest.org/)'
      - 'Page size: **800 KB** transfer size maximum.'
      - 'Requests: **15 requests** maximum.'
      - 'Pass: [Google Mobile Friendly Test](https://www.google.com/webmasters/tools/mobile-friendly/).'
      - '[Google Page Speed](https://developers.google.com/speed/pagespeed/insights/): achieve green on Mobile & green on Desktop.'


  - title: 'Validation'
    items:
      - '![](web-page-test.png)'
      - '![](mobile-friendly.png)'
      - '![](page-speed.png)'


  - title: 'Testing'
    items:
      - 'Tested with a slow/unreliable Internet connection.'
      - 'Testing in many large screen browsers & devices.'
      - 'Testing in many small screen browsers & devices.'
      - 'Achieves high grades in web performance tests.<br>[WebPageTest](http://www.webpagetest.org/), [Google Page Speed](https://developers.google.com/speed/pagespeed/insights/), [YSlow](http://yslow.org/).'
      - 'Passes [Google Mobile Friendly Test](https://www.google.com/webmasters/tools/mobile-friendly/).'


  - title: 'Design'
    items:
      - 'Conforms to your performance budget.'
      - 'Images aren’t bigger than they need to be.'
      - 'Unnecessary images have been removed.'
      - 'Images are as optimized as they can be.'
      - 'Images properly saved using “Save for Web” from Photoshop.'
      - 'All images smushed after saving them.<br>[ImageOptim](https://imageoptim.com/), [Spritebot](https://github.com/thomasjbradley/spritebot)'
      - 'As few font styles are used as possible.'
      - 'Font special features are used sparingly—no `text-rendering: optimizeLegibility`'
      - 'Appropriate PNGs have reduced colour palettes.<br>[ImageAlpha](http://pngmini.com/)'
      - 'Use CSS sprites or DataURIs where appropriate.'
      - 'Page scrolling is smooth.'
      - 'Web fonts have been sub-set to reduce file size.'
      - 'Web fonts don’t block rendering.<br>[Font Face Observer](https://github.com/bramstein/fontfaceobserver)'

  - title: 'Code'
    items:
      - 'Redundant HTML has been removed: no divitus, no hidden content, etc.'
      - 'All broken links and resources are removed.'
      - 'HTML has been minified.<br>[CloudFlare](https://www.cloudflare.com/)'
      - 'SVGs are embedded when only used on a single page.'
      - 'Offscreen images are loaded on demand.'
      - 'Put CSS `<link>` tags at the top, inside `<head>`'
      - 'Duplicate and redundant CSS has been removed.'
      - 'CSS has been concatenated and minified. <br>[Gulp](http://gulpjs.com/), [Grunt](http://gruntjs.com/), [Prepros](https://prepros.io/), [CodeKit](http://incident57.com/codekit/)'
      - 'Consider putting critical CSS in `<head>`.'
      - 'JS has been concatenated and minified.'
      - 'Put JS `<script>` tags at the bottom, right before the closing `</body>`.'
      - 'Redundant JavaScript has been removed.'
      - 'JavaScript doesn’t cause browser to hang.'
      - 'JavaScript is loaded asynchronously.'
      - 'Tracking & ad display scripts are minimum or non-existent.'


  - title: 'Server'
    items:
      - 'Resources sent in a compressed format.'
      - 'Specify character set for all text-based resources.'
      - 'Proper caching headers sent.'
      - 'Use a content delivery network (CDN) to serve your images.<br>[CloudFlare](https://www.cloudflare.com/), [KeyCDN](https://www.keycdn.com/?a=7564), [MaxCDN](http://www.maxcdn.com/)'
      - 'Website hosted on a fast server, ideally with CDN features.'
      - 'Server uses HTTP/2 where possible.'
---
