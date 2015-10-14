---
group: web-dev-4
playlist: PLWjCJDeWfDddQbBTg_lCnXyexfJpUvXDx
download: https://github.com/acgd-learn-the-web/metadata-enhanced-semantics-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/metadata-enhanced-semantics-code
checklist: seo-checklist
---

There are a bunch of standards to enhance the semantics of our websites. Search engines look for these semantics, infer information from them, and adapt their search results to them. Also, when people link to your website from social media sites you can provide defaults for the displayed content.

- **[Web 3.0](http://vimeo.com/11529540)**
- [Tim Berners-Lee: The Next Web](http://www.ted.com/talks/tim_berners_lee_on_the_next_web.html)

---

## Structured data

There are three major standards for structured data: Microdata, Microformats, and RDFa Lite. Microdata is quickly becoming the most popular and is the format that Google encourages authors to use.

Using structured data, we can enhance the semantics of our website so search engines more thoroughly understand our content.

This metadata can be used to display different results and different layouts. For example, here’s how a [recipe marked up with extra metadata shows on Pinterest](http://www.pinterest.com/pin/153192824796589716/). Google will show ratings for movies, recipe calories and much more if the information is present on the website.

**The Microdata extends all the semantics you choose in HTML—concentrate on choosing the best HTML tags first then add Microdata.**

Here’s an example [person/contact](http://schema.org/Person) marked up with Microdata:

```html
<div itemscope itemtype="http://schema.org/Person">
  <h1 itemprop="name">Sir John A. Macdonald</h1>
  <span itemprop="jobTitle">Prime Minister of Canada</span>
  <p itemprop="address" itemscope itemtype="http://schema.org/PostalAddress">
    <span itemprop="streetAddress">24 Sussex Dr.</span>
    <br>
    <span itemprop="addressLocality">Ottawa</span>,
    <span itemprop="addressRegion">ON</span>,
    <span itemprop="addressCountry">Canada</span>
    <br>
    <span itemprop="postalCode">K1A 0A3</span>
  </p>
  <dl>
    <dt>E-mail:</dt><dd><a href="mailto:primeminister@canada.ca" itemprop="email">primeminister@canada.ca</a></dd>
    <dt>Tel:</dt><dd><a href="tel:+16139416900" itemprop="telephone">613-941-6900</a></dd>
    <dt>Website:</dt><dd><a href="http://canada.ca/" itemprop="url">http://canada.ca/</a></dd>
  </dl>
</div>
```

There are a few attributes to understand form the Microdata specification:

- `itemtype` — what kind of thing you’re marking up, [there’s a big list](http://schema.org/docs/schemas.html).
- `itemscope` — defines the HTML element that surrounds all the content related to the item.
- `itemprop` — defines a single piece on content for the item.

**[☛ Browse the code to see a recipe.](https://github.com/acgd-learn-the-web/metadata-enhanced-semantics-code)**

**Links**

- **[Microdata at Schema.org](http://schema.org/)**
- [Microformats](http://microformats.org/)
- [RDFa Lite](http://rdfa.info/)
- [RDFa Lite vs. Microdata](http://manu.sporny.org/2012/mythical-differences/)
- [Schema.org markup for logos](http://googlewebmastercentral.blogspot.ca/2013/05/using-schemaorg-markup-for-organization.html)
- [Schema Creator](http://schema-creator.org/)

**Validators**

- **[Google: Rich Snippets Testing Tool](http://www.google.com/webmasters/tools/richsnippets)**
- [W3 Markup Validation Service](http://validator.w3.org/nu/)
- [Structure Data Linter](http://validator.w3.org/nu/)
- [W3 Semantic Extractor](http://www.w3.org/2003/12/semantic-extractor)

**Examples**

- [Pinterest: salad recipe](http://www.pinterest.com/pin/59532026297979167/)
- [Pinterest: sweet potato recipe](http://www.pinterest.com/pin/153192824796589716/)

---

## Social semantics

The web is an inherently social place. To encourage finding and understanding social connections we can define them in HTML using the relationship (`rel`) attribute.

### Relationships

Relationships can be defined in HTML using the `rel` attribute. These relationships semantically connect people together on the web.

```html
<!-- Linking to `me` -->
<a href="http://thomasjbradley.ca" rel="me">Thomas J Bradley</a>
<!-- Linking to my `spouse` -->
<a href="http://elizabethandjane.ca" rel="spouse">elizabeth&amp;jane photography</a>
<!-- Linking to a `friend` and a `colleague` -->
<a href="http://jedlooker.com/" rel="friend colleague">Jed Looker</a>
<!-- Linking to an `external` website -->
<a href="http://gmpg.org/xfn/creator" rel="external">XFN Creator</a>
<!-- Defining a link that represents the `home` page of your website -->
<a href="/index.html" rel="home">Home</a>
<!--
  Defining that the linked item is a download using `enclosure`
  Using the `download=""` attribute, the file will be downloaded to the computer instead of opening
  The content inside the download attribute can define its final file name
-->
<a href="/files/download.pdf" download="Download.pdf" rel="enclosure">Download Now!</a>
<!-- Linking to the `license` for this document -->
<a href="http://creativecommons.org/licenses/by-nc-sa/4.0/" rel="license">License</a>
```

**Links**

- **[Rel Values](http://microformats.org/wiki/existing-rel-values)**
- [A List Apart: Spread Your Message with Third-Party Metadata](http://alistapart.com/article/like-able-content-spread-your-message-with-third-party-metadata)
- [XFN](http://gmpg.org/xfn/)
- [XFN Creator](http://gmpg.org/xfn/creator)
- [Marking Up Relationships](http://maban.co.uk/49)
- [Open Source Protocol](http://osprotocol.com/)
- [Ultimate Guide to Link Types for Hyperlinks](http://sixrevisions.com/html/link-types-hyperlinks/)

### Open Graph

The Open Graph Protocol can be used to extract information from your website when a user links to it. It’s used by Facebook, Google+, Pinterest and more.

![](facebook-open-graph.jpg)

*You can control the information in the share preview box using the Open Graph meta tags.*

Four tags are required to support the Open Graph Protocol:

```html
<head>
  ⋮
  <meta property="og:type" content="article">
  <meta property="og:title" content="Title of this page, same as title tag">
  <meta property="og:url" content="http://fullurl.com/to-this/page/">
  <!-- Image dimensions: minimum 200x200; recommended 1500x1500 -->
  <meta property="og:image" content="http://fullurl.com/to-this/image.jpg">
  <!-- `og:site_name` is optional but highly recommended -->
  <meta property="og:site_name" content="Name of your website">
  <!-- `og:description` is also optional, but could easily be filled with the meta description -->
  <meta property="og:description" content="Description of this page, same as meta description">
  ⋮
</head>
```

There are plenty of optional tags for descriptions, author info—and more specific forms of content like: [music](http://ogp.me/#type_music), [video](http://ogp.me/#type_video), [books](http://ogp.me/#type_book), etc.

**Links**

- [Facebook Open Graph Documentation](http://developers.facebook.com/docs/opengraph/)
- [The Open Graph Protocol](http://ogp.me/)
- [Facebook Open Graph Tag Overview](http://davidwalsh.name/facebook-meta-tags)
- [Facebook Open Graph Validator](https://developers.facebook.com/tools/debug/)
- [Pinterest Rich Pins](https://developers.pinterest.com/rich_pins_overview/)
- [Pinterest Rich Pins Validator](https://developers.pinterest.com/rich_pins/validator/)
- [Using Pinterest Data Attributes and Meta Tags](https://css-tricks.com/using-pinterest-data-attributes-and-meta-tags/)

### Twitter Cards

Twitter Cards allow designers to attach supplemental information to tweets when people link to your website.

![](twitter-cards.jpg)

*You can control the information in the Twitter Card box using the Twitter meta tags.*

The default card is the “summary” card; it requires four tags:

```html
<head>
  ⋮
  <meta name="twitter:card" content="summary">
  <meta name="twitter:title" content="Title of this page, same as title tag">
  <meta name="twitter:url" content="http://fullurl.com/to-this/page/">
  <meta name="twitter:description" content="Description of this page, same as meta description">
  <!-- The image should be 120x120 pixels in dimension -->
  <meta name="twitter:image" content="http://fullurl.com/to-this/image.jpg">
  ⋮
</head>
```

There are many optional tags for larger images and different types of content like: [photos](https://dev.twitter.com/docs/cards/types/photo-card), [galleries](https://dev.twitter.com/docs/cards/types/gallery-card), [apps](https://dev.twitter.com/docs/cards/types/app-card), [media](https://dev.twitter.com/docs/cards/types/player-card), and [products](https://dev.twitter.com/docs/cards/types/product-card).

**Links**

- [Twitter Card Documentation](https://dev.twitter.com/docs/cards)
- [Markup Reference](https://dev.twitter.com/docs/cards/markup-reference)
- [Twitter Card Validator](https://dev.twitter.com/docs/cards/validation/validator)

---

## Video list

1. [Metadata: person](https://www.youtube.com/watch?v=pjihcrIsX3k&list=PLWjCJDeWfDddQbBTg_lCnXyexfJpUvXDx&index=1)
2. [Metadata: relationships](https://www.youtube.com/watch?v=7k5ZT7iak6M&list=PLWjCJDeWfDddQbBTg_lCnXyexfJpUvXDx&index=2)
3. [Metadata: social meta tags](https://www.youtube.com/watch?v=xxk21IhoSdU&list=PLWjCJDeWfDddQbBTg_lCnXyexfJpUvXDx&index=3)
