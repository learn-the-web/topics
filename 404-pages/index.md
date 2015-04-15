---
group: web-dev-4
---

A 404 error occurs when a page cannot be found on a web server.

---

## Error pages

To help make our websites more user friendly, 404 pages should be designed to help the lost user. Try to direct your user to somewhere helpful, like home or search.

Use simple language and explain what happened but don’t accuse your user. Most people don’t actually know what a 404 page is, so explain how they got there.

Try not to use “404” as the primary message on the page, using it subtly is often better.

Customized and fun 404 pages are great to cheer up your users in a negative situation, but make sure they are still extremely helpful—helpfulness before fun.

### Why would I see a 404 page?

The server will display a 404 error and page whenever a document cannot be found at the specific URL.

Here’s some examples of how that may happen:

- A mis-typed URL, or an out-of-date bookmark
- A search-engine link that’s out-of-date
- An internal broken link that hasn’t been fixed

### Other common error codes

- `401 Unauthorized` — the page can only be accessed by authorized users
- `500 Internal Server Error` — The server is having some issues

---

## Setup

Each web server has a different way to set up 404 pages. The best way to start setting up your 404 page is to create a small HTML file named `404.html` and style it. Afterwards you can set up your server to point to the document.

### GitHub

1. Create an HTML file named `404.html`
2. Put it into your GitHub repo and commit and sync it

*404 pages will only work on GitHub if you’re using a custom domain.*

**Links**

- [GitHub: Custom 404 Pages](https://help.github.com/articles/custom-404-pages)

### Apache web server

1. Create an HTML file named `404.html`
2. Make a file named `.htaccess` and put it in the root of your website
3. Put this in your `.htaccess` file:

```
ErrorDocument 404 /404.html
# You can specify pages for other error codes too
ErrorDocument 500 /500.html
```

---

## Supplemental links

- [A List Apart: The Perfect 404](http://www.alistapart.com/articles/perfect404/)
- [A List Apart: A More Useful 404](http://www.alistapart.com/articles/amoreuseful404/)
- [Smashing Magazine: 404 Error Pages, One More Time](http://www.smashingmagazine.com/2009/01/29/404-error-pages-one-more-time/)
- [HTTP/1.1 Status Code Definitions](http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html)

## Examples

- **Design gallery: <http://fab404.com/>**
- <https://github.com/404> · <https://github.com/500>
- <https://www.mint.com/404>
- <http://www.bluefountainmedia.com/404/>
- <http://www.google.ca/404>
- <http://www.lego.com/404>
- <http://www.nosh.com/404>
- <http://www.jessicahische.is/awesome/404>
- <http://www.jlern.com/404>
- <http://spigotdesign.com/404>
- <http://seesparkbox.com/404>
- <http://colly.com/404>
- <http://huwshimi.com/404/>
- <http://trentwalton.com/404>
- <http://www.hdlive09.co.uk/404>
- <http://www.getfinch.com/404>
- <http://www.alistapart.com/404>
- <http://jasonsantamaria.com/404>
- <http://gamespot.com/404>
