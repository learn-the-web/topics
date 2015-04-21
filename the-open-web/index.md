---
group: whats-next
---

The [web is an agreement](http://www.flickr.com/photos/psd/1805709102/) made up of various different components and standards and people.

> The web is agreement. Web standards are agreements we use every day.
> [Jeremy Keith](https://twitter.com/zeldman/status/100950760807870464)

---

## Three rules of web development

For a website to be true, it must follow three simple rules:

1. Can I bookmark this information? ([Stable URLs](#urls-and-links))
2. Can I go from here to there with a click? ([Hyperlinks](#urls-and-links))
3. Can I save the content locally? ([Open Accessible Formats](#the-open-web))

† [3 rules of thumb for Web development](http://www.otsukare.info/2011/08/02/3-rules-of-thumb-for-web-development)

---

## Definitions

- `The Internet` — a global computer network built on standardized protocols

- `The Web` — is a series of technologies to allow computers to easily share information
	*(World Wide Web, WWW)*

- `browser` — a piece of software that allows you to browse The Web’s documents
	*(Firefox, Internet Explorer, Chrome, Safari, Opera)*

- `domain` — a human readable name or location of a document on The Web
	*(google.com, github.com)*

- `DNS` — a system for finding where computers exist on the network given their domain
	*(Domain Name System)*

- `IP address` — 	the real name of a computer on The Internet, all computers have a unique one, usually a large string of numbers
	*(Internet Protocol Address — 125.0.0.1)*

- `URL` — a name of a location plus file requested, [and more](#urls-and-links)
	*(Uniform Resource Location — google.com/search?q=dinosaurs)*

- `server` — a computer connected to The Internet that’s sole purpose is powering some internet functionality, like a website or chat

- `host` — the same as a server, but generally a service directed at consumers purchasing web space

- `HTTP` — the communication format for talking to web servers
	*(Hypertext Transfer Protocol — HTTPS is the secure version)*

- `HTML` — the coding language used to describe content of websites
	*(Hypertext Markup Language)*

- `CSS` — the coding language used to describe how websites look
	*(Cascading Style Sheets)*

- `Javascript` — the programming language used to write more advanced interactions on websites
	*(Not to be confused with Java)*

---

## URLs and links

The primary functionality of The Web is links and URLs.

- URLs are addresses that allow us to reference different locations and resources online
- Links are the basic functionality of every website—a simple way to navigate URLs

A URL is comprised of a few different pieces, mostly human readable:

```
scheme://hostname:port/path?query#fragment
```

- `scheme` — usually “http” or “https”, the communication method the computers use to speak with each other
- `hostname` — also known as the domain, the name given to a computer on the network
- `port` — can use to different ports for communication on the computers, the default port for websites is 80 for `http` and 443 for `https`
- `path` — the file that you’d like to see on the computer
- `query` — a query that allows the file to dynamically change
- `#fragment` — also known as the hash; where in that file you want to jump to

**Links**

- [How many ways to slice a URL](http://tantek.com/2011/238/b1/many-ways-slice-url-name-pieces)
- [URLs Matter](http://paulrobertlloyd.com/2009/12/urls_matter/)
- [Do URLs Matter?](http://phpadvent.org/2009/do-urls-matter-by-david-sklar)
- [URL Design](http://warpspire.com/posts/url-design/)

---

## The Open Web

One of the primary principles of the web is openness and transparency. Tim Berners-Lee didn’t patent his invention he set if free into the public domain.

Every website relies on open source code, open technologies, and as web designers we strive to keep all our knowledge completely open and transparent.

**The source code for every website is always visible through developer tools: all their HTML, CSS, and Javascript.**

**Links**

- [Understanding The Open Web Stack](http://www.softwarequalityconnection.com/2011/08/understanding-the-open-web-stack/)
- [The Web Platform](http://platform.html5.org/)

---

## Layers of a website

Aaron Gustafson had a great analogy in his book: think of a website as a peanut M&M:

- peanut (HTML/content)
- chocolate (CSS/design)
- candy (JS/interactivity)

A peanut by itself is perfectly healthy and delicious.

A chocolate covered peanut is much sweeter and tastier, but without the peanut it’s no longer a chocolate covered peanut, it’s just a boring ball of chocolate.

A candy surrounded, chocolate covered peanut is even better, crunchy and delicious—but without the peanut it’s just a bland Smartie, without the chocolate it’s just evil sugar.

All a website needs is good content, the HTML, everything else just improves the basic experience, but is never a requirement.

† Excerpted and adapted from [“Adaptive Web Design”](http://adaptivewebdesign.info/)
