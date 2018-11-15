---
title: "SEO cheat sheet"
tags: "html semantics search engine optimization cheat sheet"
desc: "A cheat sheet covering the different important pieces of SEO."
layout: cheatsheet

groups:
  - title: 'Semantics'
    notes: 'Semantics are important because search engines use them to determine content relevance'
    items:
      - name: '`<title>`'
        details:
          - 'The `<title>` tag is shown in search results as the clickable link'
          - '&nbsp;'
          - '**Homepage title formula**'
          - |
            ```html
            <title>Site/Company Name · Small keyword rich, catchy phrase · City, Country</title>
            ```
          - '**Inside title formula**'
          - |
            ```html
            <title>Page Title · Site/Company Name</title>
            ```
          - '**Must be unique on every single page**'
          - '*Also important for accessibility*'
      - name: '`<meta description>`'
        details:
          - 'Used as the text under the link—or maybe the first `<p>` tag'
          - |
            ```html
            <meta name="description" content="A short sentence describing the purpose and content of this individual page.">
            ```
          - '**Must be unique on every single page**'
          - 'Max 140 characters'
      - name: '*Important aspects*'
        details:
          - '• `<h1>`, `<h2>`, `<h3>`, etc. & hierarchy'
          - '• First line of the first `<p>`'
          - '• `<a>` (internal & outbound)'
          - '• `<img alt="">`'
          - '• `<strong>`, `<em>`'
          - '• Page responsiveness'
          - '• Page speed'
          - '• HTTPS'
          - '• Regular updates'
          - '• Good, human-oriented content'
          - '• Domain & URLs'

  - title: 'Social tags'
    items:
      - name: '*Relationships*'
        details:
          - 'Use on `<a>` tags with the `rel` attribute'
          - '• `rel="me"` — When a link is about you'
          - '• `rel="spouse"` — When a link is about your partner'
          - '• `rel="friend"` — When a link is about your friend'
          - '• `rel="external"` — When a link points to another website'
          - '• `rel="enclosure"` — When a link points to a download'
          - '• `rel="license"` — When a link points to the license file'
          - '• `rel="nofollow"` — When search engines should ignore the link for rankings'
          - '[See more social relationships](http://microformats.org/wiki/existing-rel-values)'
      - name: '*Social media metadata*'
        details:
          - '**Facebook Open Graph**'
          - 'Add into `<head>` on every page'
          - |
            ```html
            <meta property="og:type" content="website">
            <meta property="og:locale" content="en_CA">
            <meta property="og:title" content="Title of this page, same as title tag">
            <meta property="og:url" content="http://fullurl.com/to-this/page/">
            <meta property="og:image" content="http://fullurl.com/to-this/image.jpg">
            <meta property="og:site_name" content="Name of your website">
            <meta property="og:description" content="Description of this page, same as meta description">
            ```
          - '**Twitter Cards**'
          - 'Add into `<head>` on every page'
          - |
            ```html
            <meta name="twitter:card" content="summary">
            <meta name="twitter:site" content="@yourtwitterhandle">
            <meta name="twitter:title" content="Title of this page, same as title tag">
            <meta name="twitter:url" content="http://fullurl.com/to-this/page/">
            <meta name="twitter:description" content="Description of this page, same as meta description">
            <meta name="twitter:image" content="http://fullurl.com/to-this/image.jpg">
            ```
          - '[Open Graph Protocol](http://ogp.me/)'
          - '[Twitter Card Documentation](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/summary)'
      - name: '*Geotagging & location data*'
        details:
          - 'Add into `<head>` on every page'
          - |
            ```html
            <meta name="ICBM" content="45.416667,-75.7">
            <meta name="geo.position" content="45.416667;-75.7">
            <meta name="geo.region" content="ca-on">
            <meta name="geo.placename" content="Ottawa">
            ```
          - '[ICBM address](https://en.wikipedia.org/wiki/ICBM_address#Modern_use)'
          - '[Geotagging](https://en.wikipedia.org/wiki/Geotagging#HTML_pages)'

  - title: 'Metadata'
    notes: 'There are many different [Schema.org](https://schema.org/) formats: use Microdata to embed with HTML & JSON-LD for separate details'
    items:
      - name: '*Microdata Person*'
        details:
          - 'Embedded into the HTML code'
          - |
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
                <dt>E-mail:</dt>
                <dd><a href="mailto:primeminister@canada.ca" itemprop="email">primeminister@canada.ca</a></dd>
                <dt>Tel:</dt>
                <dd><a href="tel:+16139416900" itemprop="telephone">613-941-6900</a></dd>
                <dt>Website:</dt>
                <dd><a href="http://canada.ca/" itemprop="url">http://canada.ca/</a></dd>
              </dl>
            </div>
            ```
      - name: '*JSON-LD Person*'
        details:
          - 'Separate from the HTML code, at the bottom in a `<script>` tag'
          - |
            ```html
            <script type="application/jd+json">
              {
                "@context": "https://schema.org",
                "@type": "Person",
                "name": "Sir John A. Macdonald",
                "jobTitle": "Prime Minister of Canada",
                "address": {
                  "@type": "PostalAddress",
                  "streetAddress": "24 Sussex Dr.",
                  "addressLocality": "Ottawa",
                  "addressRegion": "ON",
                  "addressCountry": "CA",
                  "postalCode": "K1A 0A3"
                },
                "email": "primeminister@canada.ca",
                "tel": "+16139416900",
                "website": "http://canada.ca/"
                "sameAs": [
                  "https://www.facebook.com/sir_john_a_macdonald",
                  "https://www.youtube.com/channel/sir_john_a_macdonald"
                  "https://www.instagram.com/sir_john_a_macdonald/",
                  "https://twitter.com/sir_john_a_macdonald",
                ]
              }
            </script>
            ```
      - name: '*JSON-LD CreativeWork*'
        details:
          - 'Separate from the HTML code, at the bottom in a `<script>` tag'
          - |
            ```html
            <script type="application/ld+json">
              {
                "@context": "https://schema.org",
                "@type": "CreativeWork",
                "name": "Branding for Dino ’R’ Us",
                "author": {
                  "@type": "Person",
                  "name": "Thomas J Bradley"
                },
                "image": "https://thomasjbradley.ca/images/dinos-r-us-logo.jpg",
                "url": "https://thomasjbradley.ca/dino-r-us/",
                "dateCreated": "2017-11-23",
                "description": "A massive rebrand for the Dinos ’R’ Us company.",
                "keywords": "dinosaurs, graphic, design, brand, logo"
              }
            </script>
            ```

  - title: 'Extra files'
    items:
      - name: '`robots.txt`'
        details:
          - '*Always include in the root of the domain.*'
          - |
            ```
            # www.robotstxt.org

            Sitemap: http://thomasjbradley.ca/sitemap.xml

            User-Agent: *
            Disallow:
            ```
      - name: '`humans.txt`'
        details:
          - 'Use the `humans.txt` to put your info & credit other people who’s work you’ve used.'
          - |
            ```
            # humanstxt.org

            # TEAM

            Designer & Developer: Thomas J Bradley <hey@thomasjbradley.ca>
            Site: http://thomasjbradley.ca
            GitHub: https://github.com/thomasjbradley
            Twitter: @thomasjbradley
            Location: Ottawa, Canada

            ---

            # THANKS

            - “Dinosaur“ by Mrs. Ste Gosaourus
              Used under CC-BY-NC-SA
              https://thenounproject.com/
            ```
      - name: '`sitemap.xml`'
        details:
          - '*Always include in the root of the domain.*'
          - |
            ```xml
            <?xml version="1.0" encoding="UTF-8"?>
            <urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">

              <url>
                 <loc>http://thomasjbradley.ca/</loc>
                 <lastmod>2058-11-23</lastmod>
                 <changefreq>monthly</changefreq>
                 <priority>0.8</priority>
              </url>

            </urlset>
            ```
          - '**Don’t forget to add an entry for every single page.**'
          - 'Consider using an automated generation tool.'
---
