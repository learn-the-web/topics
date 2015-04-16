---
group: web-dev-4
download: https://github.com/acgd-learn-the-web/search-engine-optimization-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/search-engine-optimization-code
---

Search engine optimization is important for all websites so that they’ll show up in search results.

---

## Create valuable content

The most important thing to remember about search engine optimization is to provide **real, valuable content for humans**. If it’s useful, people will link to it, tweet it, and talk about it and it will show up in search results.

### Things that matter

- *Honest, naturally keyword rich text*: if there are too many keywords for natural content, search engines will think you’re targeting them and penalize your site
- *More content than code markup*
- *Clear information hierarchy*: good navigation, good structure, good headings, etc.
- *First line of first paragraph*
- *Proper semantics*: search engines care what elements you choose and rank your content based on them
- *Faster the website the better*: Google penalizes websites that are slow
- *Links to your site from reputable sources*: the more incoming links from good, real sources, the better
- *Clean, meaningful URLs & filenames*: the words in URLs are extremely important
- *Older domains*: brand new domains have less power than domains that have existed for a while
- *Visible to search engines without barriers*: public, not behind a sign-in, not hidden by Javascript
- *Metadata*: enhanced semantics, rich information, [Microformats](http://microformats.org/), [Microdata](http://schema.org/), [RDFa Lite](http://rdfa.info/)

### Important tags

- `<title>` — the most important for keywords, also visible as the link on search results
- `<a>` — search engines look for keywords to apply to your site as well as the site you are linking to
- `<h1>`, `<h2>`, `<h3>`, etc. — very important for keywords
- `<strong>`, `<em>`
- `<meta name="description">` — sometimes used for keywords, other times not; also often used as the description in search results, but if the search engine deems it’s inappropriate something else will be used
- `<img alt="">` — Alt attributes are how search engines classify images

---

## Page title formula

Page titles are the most important piece of content on your site. We always want to front-load the titles with the best keywords.

Here’s a common formula for the `<title>` tag on your website.

### Homepage

```html
<title>Site/Company Name · Small keyword rich, catchy phrase · City, Country</title>
```

1. The website’s name or the company’s name
2. A small keyword rich and catchy phrase or tagline; 4–7 words
3. The city and country, if it’s appropriate to the website, like a small business

### Inside pages

```html
<title>Page Title · Site/Company Name</title>
```

1. The title of this page
2. The website’s name or the company’s name

By following this format we can be sure that the most important words are at the start of the title—and therefore will most likely be read.

*Every single page should have a completely unique title tag.*

The most accessible separator for title tags is the middle dot (Option + Shift + 9): [The Sound of the Accessible Title Text Separator](http://www.standards-schmandards.com/2004/title-text-separators/).

---

## Meta descriptions

The meta description tag may be used by search engines as the description underneath the link on the results page.

Search engines will determine whether the content of the meta description or the first `<p>` tag on the page is the most appropriate content for humans.

```html
<head>
	⋮
	<meta name="description" content="A short sentence describing the purpose and content of this individual page.">
	⋮
</head>
```

**Maximum length of 150 characters.**

*Every single page should have a completely unique meta description.*

---

## Sitemaps

Providing a sitemap specifically for search engines is a great way to suggest what pages exist and how important they are.

The `sitemap.xml` file is specifically formatted and targeted at search engines.

**The sitemap.xml file should be at the root of your domain:**

```
http://domain.com/sitemap.xml
```

**Links**

- [Sitemaps.org](http://www.sitemaps.org/)

---

## Robots & humans

Two other files that are very useful are targeted at robots (search engines) and humans.

- `robots.txt` — used to block search engines from seeing parts of your site; includes a reference to the `sitemap.xml` file
- `humans.txt` — a way to show who created the site, what tools where used, resources, and references

**The robots.txt file and humans.txt file should be at the root of your domain:**

```
http://domain.com/robots.txt
http://domain.com/humans.txt
```

**Links**

- [Robots.txt Spec](http://robotstxt.org/)
- [Robots Exclusion Standard](http://en.wikipedia.org/wiki/Robots_exclusion_standard)
- [Humans.txt Spec](http://humanstxt.org/)

**Example humans.txt files**

- [Disqus](http://disqus.com/humans.txt)
- [Google](http://www.google.com/humans.txt)
- [GitHub](https://github.com/humans.txt)

---

## Supplemental links

- **[Web Developers SEO Cheat Sheet](http://moz.com/blog/the-web-developers-seo-cheat-sheet-2013-edition)**
- [Google: Search Engine Optimization Starter Guide](https://static.googleusercontent.com/external_content/untrusted_dlcp/www.google.com/en//webmasters/docs/search-engine-optimization-starter-guide.pdf)
- [Common Sense SEO Checklist](http://css-tricks.com/common-sense-seo-checklist/)
- [SEO Fundamentals for Web Designers](http://webdesign.tutsplus.com/sessions/seo-fundamentals-for-web-designers/)
- [Designers SEO Checklist](http://webdesign.tutsplus.com/articles/seo-articles/seo-checklist/)
- [The Beginners Guide to SEO](http://www.seomoz.org/beginners-guide-to-seo)
- [Thoughts on SEO (39:46)](http://css-tricks.com/video-screencasts/83-thoughts-on-seo/)
- [New SEO process](http://www.seomoz.org/blog/the-new-seo-process-quit-being-kanye)
- [Writing useful page titles](http://www.456bereastreet.com/archive/201102/writing_useful_page_titles/)
- [SEO Strategies for Designers](http://www.sitepoint.com/seo-strategies-designers-part-2/)
- [Duplicate Content Penalty](http://www.webdesignfromscratch.com/seo/google-duplicate-content-penalty/)

### Tools

- **[HTML5 Outliner](http://gsnedders.html5.org/outliner/)**
- [HTML5 Outliner Chrome Extension](https://chrome.google.com/webstore/detail/afoibpobokebhgfnknfndkgemglggomo)
- **[Lynx Viewer](http://www.clickability.co.uk/lynx-viewer.php)** (Also good for checking accessibility)
- **[Google Search Engine Results Previewer](http://seo-website-designer.com/Google-SERP-Emulator)**
- [Keyword Frequency Counter](http://www.yellowpipe.com/yis/tools/wordcount/index.php)
- [Keyword Density Analyzer](http://tools.seobook.com/general/keyword-density/)
- [Complete List of Best SEO-Tools by Smashing Magazine](http://www.smashingmagazine.com/2006/09/22/complete-list-of-best-seo-tools/)

### Blogs, books & bodies

- [Building Findable Websites](http://www.amazon.ca/dp/0321526287/) by Aarron Walter
- [SEOmoz](http://www.seomoz.org/)
- [Search Engine Land](http://searchengineland.com/)
- [Matt Cutts](http://www.mattcutts.com/blog/) · [@mattcutts](https://twitter.com/mattcutts) · [The Short Cutts: The Short Answers To Every Matt Cutts Video](http://www.theshortcutts.com/)
