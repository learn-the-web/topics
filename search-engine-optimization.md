---
title: "Search engine optimization"
tags: "search engine optimization honest seo content tags meta description keywords sitemap robots humans txt"
desc: "Making sure your website shows up well in search results."
playlist: PLWjCJDeWfDddFOJYmcgNnUIhUHcsNEBTd
download: https://github.com/acgd-learn-the-web/search-engine-optimization-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/search-engine-optimization-code
checklist: seo-checklist
extra_practice:
  week:
    title: "Web Dev 5, Week 07"
    url: "/courses/web-dev-5/week-07/"
  slides:
    - title: "SEO & metadata"
      url: "/courses/web-dev-5/seo-metadata/"
  lessons:
    - title: "Robot Parts Co."
      url: "/courses/web-dev-5/robot-parts-co/"
  activities:
    - title: "Search Seer"
      url: "search-seer"
---

Search engine optimization is important for all websites so that they’ll show up in search results.

---

## Create valuable content

The most important thing to remember about search engine optimization is to provide **real, valuable content for humans**. If it’s useful, people will link to it, share it, and talk about it and it will show up in search results.

### Things that matter

When search engines spider your website they base the search results on specific things in your website. We don’t know the exact formula for how your pages are ranked, but there are things that should be prioritized.

- **Honest, naturally keyword rich text**: if there are too many keywords for natural content, search engines will think you’re targeting them and penalize your site.
- **More content than code markup**.
- **Clear information hierarchy**: good navigation, good structure, good headings, etc..
- **First line of first paragraph**.
- **Proper semantics**: search engines care what elements you choose and rank your content based on them.
- **Faster the website the better**: search engines penalize websites that are slow.
- **Links to your site from reputable sources**: the more incoming links from good, real sources, the better.
- **Clean, meaningful URLs & filenames**: the words in URLs are extremely important.
- **Older domains**: brand new domains have less power than domains that have existed for a while.
- **Visible to search engines without barriers**: public, not behind a sign-in, not hidden by JavaScript.
- **Metadata**: enhanced semantics, rich information.
  [☛ Learn more about metadata.](/topics/metadata-enhanced-semantics/)
- **Mobile friendliness:** if your website is responsive and mobile friendly it will get better rankings.
- **Security**: websites served over HTTPS get better search rankings.

### Important tags

Certain tags in your HTML content carry more weight than others, so be sure to put important keywords into these tags.

1. `<title>` — the most important for keywords, also visible as the link on search results.
2. `<meta name="description">` — sometimes used for keywords, other times not; also often used as the description in search results, but if the search engine deems it’s inappropriate something else will be used.
3. `<h1>`, `<h2>`, `<h3>`, etc. — very important for keywords.
4. First line of the first `<p>…</p>` — can be used for the description in search results.
5. `<a>` — search engines look for keywords to apply to your site as well as the site you are linking to.
6. `<img alt="">` — Alt attributes are how search engines classify images.
7. `<strong>`, `<em>`.

---

## Results page content

The content displayed on the search results page comes from a few different places.

![](search-results.jpg)

1. **The big link** — this is the `<title>` tag of your website, so make sure it counts.
2. **The description** — comes either from your `meta description` or the first line of your first paragraph.
3. **The URL** — is the URL of your website, keywords count.
4. **Extra navigation** — you have no control over these, the search engine will add them if it likes.
5. **Extra metadata** — is controlled by the extra metadata you add to your website.
  [☛ Learn more about metadata.](/topics/metadata-enhanced-semantics/)

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
https://example.ca/sitemap.xml
```

The sitemap file is a plain text file with an XML format. Every page in your website should be listed inside it.

Here’s a basic example:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">

  <url>
    <!-- The <loc> tag is the only one that’s required. -->
    <loc>https://domain.ca</loc>
    <!-- OPTIONAL: Priority will default to 0.5 but can go up to 1.0. -->
    <priority>1.0</priority>
    <!-- OPTIONAL: Must be in this format -->
    <lastmod>2005-01-01</lastmod>
    <!-- OPTIONAL: can be always, hourly, daily, weekly, monthly, yearly, never -->
    <changefreq>monthly</changefreq>
  </url>

  <!-- If you want to add another page, add another <url> tag -->
  <url>
    <loc>https://domain.ca/about/</loc>
  </url>

</urlset>
```

Unless your website is really small, most often the sitemap file is automatically generated with a tool instead of being written by hand.

After you’ve set up your sitemap.xml file, some search engines like Google & Bing allow you to upload it to their webmaster tools to encourage the search engines to spider your website.

**Links**

- [Sitemaps.org](http://www.sitemaps.org/)

---

## Robots & humans

Two other files that are very useful are targeted at robots (search engines) and humans.

- `robots.txt` — used to block search engines from seeing parts of your site; includes a reference to the `sitemap.xml` file
- `humans.txt` — a way to show who created the site, what tools where used, resources, and references

**The robots.txt file and humans.txt file should be at the root of your domain:**

```
https://example.ca/robots.txt
https://example.ca/humans.txt
```

### Robots.txt

A robots.txt file is a plain text file, with a very simple structure.

```
User-Agent: *
Disallow: /img
```

The above robots.txt file would stop search engines from allowing your images to show up in the search results.

The `User-Agent` line allows you to specify specific search engines, if you want different rules for different engines, e.g. `googlebot`, `msnbot`, etc.

If you want to disallow more things, just add more disallow lines:

```
User-Agent: *
Disallow: /img
Disallow: /fonts
Disallow: /video
```

*The robots files is not for hiding secret things, as soon as it’s listed in robots.txt it’s no longer secret.*

You should also specify the location of your sitemap.xml file inside the robots.txt file—in fact this is where search engines look to find your sitemap.xml.

The robots.txt file that I use in almost all my websites looks like this:

```
Sitemap: https://example.ca/sitemap.xml

User-Agent: *
```

I’m specifically not disallowing anything from search engines.

**The robots.txt file is required for all domains.** Search engines will look for it and if it isn’t found, your website stats will show many 404 errors.

### Humans.txt

The humans.txt file is optional. It’s a place to write about who created the website and how it was created, like credits in a movie.

Since it’s targeted at human beings there isn’t any specific format, but looking at the standard there are a few sections that are recommended.

- **Team** — a list of people who are involved, emails, locations, etc.
- **Thanks** — where you can credit assets used in your website: icons, stock photos, etc.
- **Technology** — where you can list the tools and technology you used in creating the site.

There are extensions you can get for your browser that highlight what websites have a humans.txt file: [Firefox](https://addons.mozilla.org/en-US/firefox/addon/humanstxt/), [Chrome](https://chrome.google.com/webstore/detail/humanstxt/pocdghmbbodjiclginddlaimdaholhfk).

**Links**

- [Robots.txt Spec](http://www.robotstxt.org/)
- [Robots Exclusion Standard](http://en.wikipedia.org/wiki/Robots_exclusion_standard)
- [Humans.txt Spec](http://humanstxt.org/)

**Example humans.txt files**

- [Disqus](http://disqus.com/humans.txt)
- [Google](http://www.google.com/humans.txt)
- [GitHub](https://github.com/humans.txt)

---

## Video list

1. [SEO: where search engine results come from](https://www.youtube.com/watch?v=bpE-bIX1z9M&index=1&list=PLWjCJDeWfDddFOJYmcgNnUIhUHcsNEBTd)
2. [SEO: important content](https://www.youtube.com/watch?v=OaWvHoj7HXo&index=2&list=PLWjCJDeWfDddFOJYmcgNnUIhUHcsNEBTd)
3. [SEO: title tag formula](https://www.youtube.com/watch?v=EXB0dEACACE&index=3&list=PLWjCJDeWfDddFOJYmcgNnUIhUHcsNEBTd)
4. [SEO: sitemap.xml](https://www.youtube.com/watch?v=_CKevzKuZLc&index=4&list=PLWjCJDeWfDddFOJYmcgNnUIhUHcsNEBTd)
5. [SEO: robots.txt & humans.txt](https://www.youtube.com/watch?v=Y7uaHd-KrvU&index=5&list=PLWjCJDeWfDddFOJYmcgNnUIhUHcsNEBTd)

## Supplemental links

- **[Web Developers SEO Cheat Sheet](http://moz.com/blog/the-web-developers-seo-cheat-sheet-2013-edition)**
- [Google: Search Engine Optimization Starter Guide](https://static.googleusercontent.com/external_content/untrusted_dlcp/www.google.com/en//webmasters/docs/search-engine-optimization-starter-guide.pdf)
- [Common Sense SEO Checklist](https://css-tricks.com/common-sense-seo-checklist/)
- [SEO Fundamentals for Web Designers](http://webdesign.tutsplus.com/sessions/seo-fundamentals-for-web-designers/)
- [Designers SEO Checklist](http://webdesign.tutsplus.com/articles/seo-articles/seo-checklist/)
- [The Beginners Guide to SEO](http://www.seomoz.org/beginners-guide-to-seo)
- [Thoughts on SEO (39:46)](https://css-tricks.com/video-screencasts/83-thoughts-on-seo/)
- [New SEO process](http://www.seomoz.org/blog/the-new-seo-process-quit-being-kanye)
- [Writing useful page titles](http://www.456bereastreet.com/archive/201102/writing_useful_page_titles/)
- [SEO Strategies for Designers](http://www.sitepoint.com/seo-strategies-designers-part-2/)
- [Duplicate Content Penalty](http://www.webdesignfromscratch.com/seo/google-duplicate-content-penalty/)
- [SEO Checklist 2015](http://onlinemarketinginct.com/2015/05/09/seo-checklist-2015/)
- [SEO Cheat Sheet](https://moz.com/blog/seo-cheat-sheet)
- [HEAD](https://gethead.info/)

### Tools

- **[HTML5 Outliner](http://gsnedders.html5.org/outliner/)**
- [HTML5 Outliner Chrome Extension](https://chrome.google.com/webstore/detail/afoibpobokebhgfnknfndkgemglggomo)
- **[Lynx Viewer](http://www.clickability.co.uk/lynx-viewer.php)** (Also good for checking accessibility)
- **[Google Search Engine Results Previewer](http://www.serpsimulator.com/)**
- [Keyword Frequency Counter](http://www.yellowpipe.com/yis/tools/wordcount/index.php)
- [Keyword Density Analyzer](http://tools.seobook.com/general/keyword-density/)
- [Complete List of Best SEO-Tools by Smashing Magazine](http://www.smashingmagazine.com/2006/09/22/complete-list-of-best-seo-tools/)
- [Varvy SEO](https://varvy.com/)

### Blogs, books & bodies

- [Building Findable Websites](http://www.amazon.ca/dp/0321526287/) by Aarron Walter
- [SEOmoz](http://www.seomoz.org/)
- [Search Engine Land](http://searchengineland.com/)
- [Matt Cutts](http://www.mattcutts.com/blog/) · [@mattcutts](https://twitter.com/mattcutts) · [The Short Cutts: The Short Answers To Every Matt Cutts Video](http://www.theshortcutts.com/)
