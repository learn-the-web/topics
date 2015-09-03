---
group: web-dev-4
playlist:
---

---

## Advanced image compression

### ImageAlpha + PNG8

### Blurring JPEGs to reduce file size

### Optimized favicons

### Embedding single-use SVGs

### Data URIs

**Links**

- [Instagram and Optimizing Favicons](https://zoompf.com/blog/2012/04/instagram-and-optimizing-favicons)
- []()
- []()
- []()

---

## Minification

### CSS minification & concatenation

### JS minification & concatenation

### Minification tools

#### Automatic minification with CloudFlare

**Links**

- [Gulp for Beginners](https://css-tricks.com/gulp-for-beginners/)
- []()
- []()
- []()
- []()

---

## Server considerations

### Compressing code files

### Caching headers

### Automatic server setup with CloudFlare

**Links**

- [Web Caching Basics: Terminology, HTTP Headers, and Caching Strategies](https://www.digitalocean.com/community/tutorials/web-caching-basics-terminology-http-headers-and-caching-strategies)
- [The Difference Between Minification and Gzipping](https://css-tricks.com/the-difference-between-minification-and-gzipping/)
- []()
- []()

---

## Content delivery networks

Content delivery networks (CDNs) allow us to distribute our resources around the world on lots of different servers. Then when a user downloads our website they receive the file from the server that’s closest to them making it download more quickly.

Most often we put our static files on CDNs, primarily images, because they’re the files that most benefit from CDNs.

### CloudFlare

CloudFlare is a very popular CDN with lots of great free features. But not only do they provide CDN features—automatically—they also perform other performance tasks: like minification, caching headers, gzipping and more.

[CloudFlare becomes our DNS provider](https://github.com/algonquindesign/resources/tree/master/domains#better-security-and-performance-with-cloudflare) and these options are fairly automatic after setting up.

They even provide a bunch of security features like DDOS protection and free SSL for websites.

*If you’re hosting on GitHub you’ll have to use a [custom domain](https://github.com/algonquindesign/resources/tree/master/domains) in order to take advantage of CloudFlare.*

### KeyCDN

**Links**

- [Know When to CDN](http://www.kendoui.com/blogs/teamblog/posts/13-11-07/know-when-to-cdn.aspx)
- **[CloudFlare](https://www.cloudflare.com/)** — also provides security, minification, caching headers
- **[KeyCDN](https://www.keycdn.com/)**
- [cdnjs](http://cdnjs.com/)
- [MaxCDN](http://www.maxcdn.com/)
- [Coral CDN](http://www.coralcdn.org/)
- [Amazon CloudFront](http://aws.amazon.com/cloudfront/)
- [Kraken.io](https://kraken.io/)

---

## Other performance considerations

### Rendering performance

#### Critical CSS

#### Fonts

##### Font features
text-rendering: optimizeLegibility

### Scrolling performance

### Battery drain

### CPU load & memory usage

**Links**

- [The @font-face dilemma](https://viget.com/extend/the-font-face-dilemma)
- [CSS Triggers… A game of layout, paint, and composite.](http://csstriggers.com/)
- [Everything You Need to Know About the CSS will-change Property](https://dev.opera.com/articles/css-will-change-property/)
- [Fix scrolling performance with CSS will-change property](https://fourword.fourkitchens.com/article/fix-scrolling-performance-css-will-change-property)
- [Use Gulp to automate your critical path CSS](http://fourword.fourkitchens.com/article/use-gulp-automate-your-critical-path-css)
- [Understanding Critical CSS](http://www.smashingmagazine.com/2015/08/understanding-critical-css/)

---

## Video list

## Supplemental links

- [Designing for Performance](http://designingforperformance.com/)
- [Breaking news at 1000ms](https://speakerdeck.com/patrickhamann/breaking-news-at-1000ms-front-trends-2014)
- [Google Web Fundamentals: Performance](https://developers.google.com/web/fundamentals/performance/)
- [Performance Tools](https://css-tricks.com/performance-tools/)
- [More Weight Doesn’t Mean More Wait](https://www.filamentgroup.com/lab/weight-wait.html)
- [Website Performance Checklist](http://websiteperformancechecklist.com/)
- [Performance & Organization](http://learn.shayhowe.com/advanced-html-css/performance-organization/)
