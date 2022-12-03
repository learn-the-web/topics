---
title: "JavaScript templates"
tags: "javascript templates mustache handlebars separate separation concerns external html"
desc: "Separating the HTML and JavaScript by using templates."
playlist: javascript-templates
download: https://github.com/learn-the-web/javascript-templates-code/archive/master.zip
github: https://github.com/learn-the-web/javascript-templates-code
---

Separating our HTML from our JavaScript into small reusable pieces.

---

## Templates

Just like not having CSS in our JavaScript, we don’t want to cross the streams with our HTML—so templates allow us to keep our HTML in the HTML file and not have it in our JavaScript code.

### Mustache

There are lots of different JavaScript template engines; one really popular one is Mustache.

In our HTML we would provide the template, like this:

```html
<script id="template" type="x-tmpl-mustache">
  <h1>Hello {{name}}!</h1>
</script>
```

Using JavaScript, we can read the template and put some information into it:

```js
// Mustache uses objects to represent the data for the template
var data = {
  name: 'Thomas'
};

// We grab the template from our HTML and get it ready
var template = $('#template').html();
Mustache.parse(template);

// Then we take the template and render it with our data
var rendered = Mustache.render(template, data);

// We could then insert the rendered HTML into our page
$('body').html(rendered);
```

**Links**

- [Mustache](http://mustache.github.io/)
- [Mustache documentation](https://github.com/janl/mustache.js)
- [Handlebars](http://handlebarsjs.com/)

---

## Video list

1. [JavaScript DOM: Templates](https://videos.learntheweb.courses/playlists/javascript-templates/#1-templates)
2. [JavaScript DOM: Templates & forms](https://videos.learntheweb.courses/playlists/javascript-templates/#2-templates-forms)
3. [JavaScript DOM: Event delegation](https://videos.learntheweb.courses/playlists/javascript-templates/#3-event-delegation)
