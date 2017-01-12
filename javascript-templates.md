---
title: "Javascript templates"
tags: "javascript templates mustache handlebars separate separation concerns external html"
desc: "Separating the HTML and Javascript by using templates."
download: https://github.com/acgd-learn-the-web/javascript-templates-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/javascript-templates-code
---

Separating our HTML from our Javascript into small reusable pieces.

---

## Templates

Just like not having CSS in our Javascript, we don’t want to cross the streams with our HTML—so templates allow us to keep our HTML in the HTML file and not have it in our Javascript code.

### Mustache

There are lots of different Javascript template engines; one really popular one is Mustache.

In our HTML we would provide the template, like this:

```html
<script id="template" type="x-tmpl-mustache">
	<h1>Hello {{name}}!</h1>
</script>
```

Using Javascript, we can read the template and put some information into it:

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

1. [Javascript DOM: templates](https://www.youtube.com/watch?v=3EJ3rf-Yk0g&index=7&list=PLWjCJDeWfDdexVfek9nZEdmbyBL6_yP6Y)
2. [Javascript DOM: templates & forms](https://www.youtube.com/watch?v=xQ-Y3APkbvQ&index=8&list=PLWjCJDeWfDdexVfek9nZEdmbyBL6_yP6Y)
3. [Javascript DOM: event delegation](https://www.youtube.com/watch?v=cWTI3er8EKI&index=9&list=PLWjCJDeWfDdexVfek9nZEdmbyBL6_yP6Y)
