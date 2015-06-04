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

## Web terminology

- `Internet` — A globally connected series of computers that runs lots of services including the Web, e-mail, chat, etc.
- `Web, WWW` — The World Wide Web: a document and application service built with standardized technologies, allowing computers to share open information.
- `DNS` — Domain Name System: a system that allows humans to find computers on the Internet by changing the human-readable URL into a machine readable IP address.
- `Domain` — The human readable name of a website, or the name/address of a computer connected to the Web. *(algonquindesign.ca, github.com)*
- `TLD` — Top Level Domain: the last part of a domain, found at the end, often used to describe the purpose or location of the domain: “.com”, “.ca”, “.edu”, etc.
- `HTTP(S)` — Hypertext Transfer Protocol: the communication protocol that computers use to talk to each other on the Web. `HTTPS` is the encrypted version of the communication protocol.
- `Server` — A computer connected to the Internet that contains lots of functionality to run Internet services and send websites.
- `Host` — Pretty much the same as a server, but more targeted at consumers, a place to put your website online.
- `IP` — Internet Protocol, used colloquially for IP Address: the computer-readable name/address of an Internet connected to computer. *(125.0.0.1)*
- `URL` — Uniform Resource Locator: The human-readable address to a website, including the domain and the path. *(http://www.google.com/search?q=dinosaurs)*
- `Path` — Part of a URL, the section that follows a domain, describing what resources to view on the server.
- `Browser` — A piece of software on your computing device that allows you to use the Web, it renders your websites and allows you to interact with them. *(Firefox, Internet Explorer, Chrome, Safari, Opera)*
- `W3C` — The World Wide Web Consortium: a group of companies and individuals who work on standardizing all the web technologies.
- `HTML` — Hypertext Markup Language: the coding language used to describe the content on all webpages.
- `CSS` — Cascading Style Sheets: the coding language used to describe how websites look.
- `Javascript` — The programming language used to add extra interactivity to websites.

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
- [URL Design](http://warpspire.com/posts/url-design/)

---

## The Open Web

One of the primary principles of the web is openness and transparency. Tim Berners-Lee didn’t patent his invention he set if free into the public domain.

Every website relies on open source code, open technologies, and as web designers we strive to keep all our knowledge completely open and transparent.

**The source code for every website is always visible through developer tools: all their HTML, CSS, and Javascript.**

**Links**

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
