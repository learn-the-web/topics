---
group: web-dev-4
playlist:
---

---

## Basic performance first

There’s a whole lot you can do to make your website faster before getting to these steps.

**[☛ Make sure you follow all the steps in the basic performance tutorial first.](/topics/performance/)**

---

## Advanced resource compression

### ImageAlpha + PNG8

### Blurring JPEGs to reduce file size

### Optimized favicons

### Embedding single-use SVGs

### Sub-setting fonts

### Data URIs

**Links**

- **[ImageAlpha](http://pngmini.com/)**
- **[FontSquirrel Web Font Generator](http://www.fontsquirrel.com/tools/webfont-generator)**
- [Instagram and Optimizing Favicons](https://zoompf.com/blog/2012/04/instagram-and-optimizing-favicons)
- [Data URI Converter](https://datauriconverter.appspot.com/)
- [Image2Base64](http://image2base64.wemakesites.net/)

---

## Minification

Minification is the like smushing images, but for code. It removes all the extra characters, all the white space, all the tabs—everything that’s helpful for humans and unnecessary for computers. Resulting in a smaller file size.

Concatenation is just a fancy word for combining.

### CSS & JS minification & concatenation

We use these two processes on our CSS and Javascript files. Combine together all our CSS files into one file and strip all the extra stuff to make them download faster. We even combine all our Javascript files together, strip the whitespace, and some minifiers even rename functions to a single letter to save space.

#### CSS minification example

Here’s an idea of what CSS will look like before and after minification.

Before:

```css
body {
  color: red;
  font: sans-serif;
}

h1 {
  color: green;
  font-weight: bold;
}
```

After:

```css
body{color:red;font:sans-serif;}h1{color:green;font-weight:bold;}
```

The computer can’t tell the difference between the two pieces of code, and it saves us a lot in download time.

#### JS minification example

Here’s what Javascript might look like before and after minification.

Before:

```js
var $btn = $('.btn');
var onBtnClick = function (e) {
  $btn.addClass('is-active');
}

$btn.on('click', onBtnClick);
```
After:

```js
var a=$('.btn'),b=function(){a.addClass('is-active')};a.on('click',b);
```

Notice how the variables and functions have been renamed and simplified.

### Minification naming

After your files have been minified it’s convention to append the `.min` extension onto them.

**Never delete the original source file. Always keep the original and the minified versions.**

For CSS you’ll end up with something like this:

```
main.css
main.min.css
```

### Minification tools

Minification is a process that shouldn’t be done by hand, but should be automated by a tool. There are lost of different tools, manual & automatic, GUI & command line. Many of these tools will even automatically minify when you save your file. *Choose the one that works best for you.*

#### GUI tools

GUI tools provide an interface where you can drag and drop a project folder. The tool will detect CSS and Javascript files and minify them for you.

Some popular GUI tools are [Prepros](https://prepros.io/) & [CodeKit](http://incident57.com/codekit/).

#### Command-line tools

Command-line tools are extremely popular (and this is how I do it). They have many advantages over GUI tools but are slightly more complicated to get running.

Some of the popular command-line tools are **[Gulp](http://gulpjs.com/)** & [Grunt](http://gruntjs.com/). The tools are really just task runners, they delegate to other pieces of code to do the minification and concatenation.

- For CSS a popular minifier is [cssnano](http://cssnano.co/).
- For JS the most widely used minifier is [UglifyJS](http://lisperator.net/uglifyjs/).

These minifiers can be run without a task runner, but it’s a much less manual if you use something like Gulp.

##### Concatenation with Jekyll

If you’re using Jekyll you can use its include system to concatenate CSS and Javascript.

**[☛ Watch a video on concatenating CSS with Jekyll.](https://www.youtube.com/watch?v=H4Fc2xL79nU&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=28)**

#### Automatic minification with CloudFlare

If your CSS and Javascript files are already concatenated, then you can get CloudFlare to automatically minify them for you. This works really well if you’re using Jekyll to combine files.

![](cloudflare-minify.jpg)

Go to the “Speed” section and check all the options in “Auto Minify̦”.

**Links**

- **[Gulp](http://gulpjs.com/)**
- [Gulp for Beginners](https://css-tricks.com/gulp-for-beginners/)
- [Grunt](http://gruntjs.com/)
- [Prepros](https://prepros.io/)
- [CodeKit](http://incident57.com/codekit/)
- [cssnano](http://cssnano.co/)
- [UglifyJS](http://lisperator.net/uglifyjs/)

---

## Server considerations

### Compressing code files

### Caching headers

### Automatic server setup with CloudFlare

**Links**

- [Web Caching Basics: Terminology, HTTP Headers, and Caching Strategies](https://www.digitalocean.com/community/tutorials/web-caching-basics-terminology-http-headers-and-caching-strategies)
- [The Difference Between Minification and Gzipping](https://css-tricks.com/the-difference-between-minification-and-gzipping/)

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

#### Fonts

##### Font features
text-rendering: optimizeLegibility

#### Inlining critical CSS

##### Inlining CSS for single page websites

### Scrolling performance

### Battery drain, CPU load & memory usage

**Links**

- [The @font-face dilemma](https://viget.com/extend/the-font-face-dilemma)
- [LocalFont](http://jaicab.com/localFont/)
- [How we use web fonts responsibly, or, avoiding a @font-face-palm](https://www.filamentgroup.com/lab/font-loading.html)
- [Font Loading Revisited with Font Events](https://www.filamentgroup.com/lab/font-events.html)
- [CSS Triggers… A game of layout, paint, and composite.](http://csstriggers.com/)
- [Everything You Need to Know About the CSS will-change Property](https://dev.opera.com/articles/css-will-change-property/)
- [Fix scrolling performance with CSS will-change property](https://fourword.fourkitchens.com/article/fix-scrolling-performance-css-will-change-property)
- [Use Gulp to automate your critical path CSS](http://fourword.fourkitchens.com/article/use-gulp-automate-your-critical-path-css)
- [Understanding Critical CSS](http://www.smashingmagazine.com/2015/08/understanding-critical-css/)

---

## Video list

1. [Advanced performance: imageAlpha + PNG8]()
2. [Advanced performance: blurring JPGs]()
3. [Advanced performance: optimizing favicons]()
4. [Advanced performance: sub-setting fonts]()
5. [Advanced performance: data URIs]()
6. [Advanced performance: CSS, JS minification & concatenation?]()
7. [Advanced performance: content delivery networks]()
8. [Advanced performance: CloudFlare settings]()
9. [Advanced performance: scrolling performance]()

## Supplemental links

- [Designing for Performance](http://designingforperformance.com/)
- [Breaking news at 1000ms](https://speakerdeck.com/patrickhamann/breaking-news-at-1000ms-front-trends-2014)
- [Google Web Fundamentals: Performance](https://developers.google.com/web/fundamentals/performance/)
- [Performance Tools](https://css-tricks.com/performance-tools/)
- [More Weight Doesn’t Mean More Wait](https://www.filamentgroup.com/lab/weight-wait.html)
- [Website Performance Checklist](http://websiteperformancechecklist.com/)
- [Performance & Organization](http://learn.shayhowe.com/advanced-html-css/performance-organization/)
- [Prefetching, preloading, prebrowsing](https://css-tricks.com/prefetching-preloading-prebrowsing/)
