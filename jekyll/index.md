---
group: web-dev-4
playlist: PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-
download: https://github.com/acgd-learn-the-web/jekyll-code/archive/gh-pages.zip
github: https://github.com/acgd-learn-the-web/jekyll-code
livewebsite: /jekyll-code/
---

Jekyll is a static website generator—it helps making websites more efficient by reducing duplication.

- Makes use of Markdown to reduce the overhead of HTML
- Allows sharing of HTML code between pages
- Has the ability to automatically write repeated HTML
- Can be hosted on GitHub using GitHub pages

---

## Jekyll Installation

Jekyll is a command line tool, it requires the Apple command line tools to be installed.

You can use this to install the command line tools in Mac OS X 10.9 or higher:

```bash
$ xcode-select --install
```

After installing the command line tools and opening Terminal on your Mac, there are two commands that must be run:

```bash
$ sudo gem update --system
$ sudo gem install jekyll
```

**Links**

- **[☛ Jekyll installation](/topics/jekyll-installation/)**
- [Jekyll Docs: installation](http://jekyllrb.com/docs/installation/)

---

## Setting up Jekyll

To set up a Jekyll project you must add a `_config.yml`.

Here’s a sample config file:

```yaml
baseurl: /your-folder-on-github
exclude: []
```

**Links**

- **[Setting up GitHub Pages Reference](https://github.com/algonquindesign/resources/tree/master/github-pages)**
- [Jekyll Docs: Directory structure](http://jekyllrb.com/docs/structure/)
- [Jekyll Docs: Configuration](http://jekyllrb.com/docs/configuration/)

---

## Running Jekyll

Jekyll must be running in the Terminal when you are actively developing a project.


**Start**

```bash
$ jekyll serve --watch --baseurl ""
```

**Stop**

```
Control + C
```

**Links**

- **[Jekyll terminal cheat sheet](/topics/jekyll-terminal-guide/)**
- [Jekyll Docs: Quick-start guide](http://jekyllrb.com/docs/quickstart/)
- [Jekyll Docs: Usage](http://jekyllrb.com/docs/usage/)

---

## Layouts

Jekyll has a feature named layouts that allows designers to put the header and footer in a single file and have them shared between every page on the site.

Inside your `index.html`:

```html
---
layout: default
---

<h1>Homepage</h1>
```

We must specify what layout the HTML page will use at the top using YAML front matter.

The layouts must go into a folder named `_layouts`:

```html
<!DOCTYPE html>
<html lang="en-ca">
<head>
	<meta charset="utf-8">
	<title>Website</title>
</head>
<body>
	{{content}}
</body>
</html>
```

The `{{content}}` placeholder is where Jekyll will place the content from the `index.html`.

**Links**

- [Jekyll Docs: Templates](http://jekyllrb.com/docs/templates/)

---

## Posts

Jekyll supports posts, like blog posts, that can be used as an ordered type of content.

Posts must be named very strictly and stored inside the `_posts` folder:

```
_posts/
	2013-09-26-water-in-martian-dirt.md
	2013-10-06-clouds-on-kepler-7b-mapped.md
	2013-10-09-planet-without-star.md
```

**The post’s file name must begin with a properly formatted date, in the format: `YYYY-MM-DD`.**

To display a list of posts in your website, you can use Jekyll’s loop:

```html
<ul>
	{% for post in site.posts %}
		<li>
			<a href="{{site.baseurl}}{{post.url}}">{{post.title}}</a>
			<p>{{post.excerpt}}</p>
		</li>
	{% endfor %}
</ul>
```

**Links**

- [Jekyll Docs: Posts](http://jekyllrb.com/docs/posts/)

---

## Video list

1. [Jekyll: installation](https://www.youtube.com/watch?v=IINPHVVrF5Q&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=1)
2. [Jekyll: setting up on GitHub](https://www.youtube.com/watch?v=jVeNnHy65Rs&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=2)
3. [Jekyll: setting up a Jekyll project](https://www.youtube.com/watch?v=cH9T9yRZ33c&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=3)
4. [Jekyll: starting and stopping](https://www.youtube.com/watch?v=Vvh-PWMOf4g&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=4)
5. [Jekyll: the _site folder](https://www.youtube.com/watch?v=C6H2U_ZA99o&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=5)
6. [Jekyll: layouts](https://www.youtube.com/watch?v=ra8r2VymK3c&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=6)
7. [Jekyll: creating navigation](https://www.youtube.com/watch?v=fX3jpJlaDHI&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=7)
8. [Jekyll: site baseurl](https://www.youtube.com/watch?v=SgC4L9mCNgs&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=8)
9. [Jekyll: includes](https://www.youtube.com/watch?v=lelmLpXbUEo&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=9)
10. [Jekyll: adding CSS](https://www.youtube.com/watch?v=RA9N9EywXa0&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=10)
11. [Jekyll: highlighting navigation](https://www.youtube.com/watch?v=T7ApyjWO3nQ&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=11)
12. [Jekyll: include parameters](https://www.youtube.com/watch?v=TJcn_PJ2100&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=12)
13. [Jekyll: looping over posts](https://www.youtube.com/watch?v=9ePPr5rOszc&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=13)
14. [Jekyll: post categories](https://www.youtube.com/watch?v=pAay92BHBPo&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=14)
15. [Jekyll: limiting the post loop](https://www.youtube.com/watch?v=Xn8W0qf5xi4&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=15)
16. [Jekyll: nested layouts](https://www.youtube.com/watch?v=A6x1mFRmVX0&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=16)
17. [Jekyll: highlighting navigation on multiple pages](https://www.youtube.com/watch?v=ZMA8SN9_xsM&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=17)
18. [Jekyll: nested layouts for a specific content type](https://www.youtube.com/watch?v=rcRiJSaPwbc&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=18)
19. [Jekyll: using posts for ordered content](https://www.youtube.com/watch?v=yLptLUVoz3k&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=19)
20. [Jekyll: putting pages inside folders](https://www.youtube.com/watch?v=U9wq_94mY6c&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=20)
21. [Jekyll: looping over pages](https://www.youtube.com/watch?v=icRJhLg6eps&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=21)
22. [Jekyll: includes with page loops](https://www.youtube.com/watch?v=9vhCxZgV1HA&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=22)
23. [Jekyll: page loops and images](https://www.youtube.com/watch?v=q-ptiIokeLY&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=23)
24. [Jekyll: advanced nested layouts for specific content types](https://www.youtube.com/watch?v=dUwF_0NRbu8&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=24)
25. [Jekyll: page sub-folders](https://www.youtube.com/watch?v=q6MSEnTpGPY&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=25)
26. [Jekyll: generating page navigation](https://www.youtube.com/watch?v=gel_0pwjo78&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=26)
27. [Jekyll: changing background images](https://www.youtube.com/watch?v=OQhNqdB-ino&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=27)
28. [Jekyll: many CSS files](https://www.youtube.com/watch?v=H4Fc2xL79nU&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=28)
29. [Jekyll: unique titles for every page](https://www.youtube.com/watch?v=ra9Td0DpK0s&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=29)
30. [Jekyll: meta description](https://www.youtube.com/watch?v=FUL9SSgMZ8Y&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=30)
31. [Jekyll: automatic sitemap.xml](https://www.youtube.com/watch?v=C49lhiX_JO0&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=31)
32. [Jekyll: pretty URLs](https://www.youtube.com/watch?v=sc-4FywBPlg&list=PLWjCJDeWfDdfVEcLGAfdJn_HXyM4Y7_k-&index=32)

## Supplemental links

- **[Setting up GitHub Pages Reference](https://github.com/algonquindesign/resources/tree/master/github-pages)**
- [Jekyll Documentation](http://jekyllrb.com/)
- [Jekyll Setting Up on GitHub Pages](http://jekyllrb.com/docs/github-pages/)
- [Shopify: Liquid for Designers](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers)
- [Shopify: Liquid Basics](http://docs.shopify.com/themes/liquid-basics)
- [Jekyll by Example](http://www.andrewmunsell.com/tutorials/jekyll-by-example/)
