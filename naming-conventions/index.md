---
group: web-dev-1
---

Some common conventions to follow when developing websites.

---

## File names

1. **All lowercase**
2. **No spaces!**
3. Only letters, numbers, underscores (_), and dashes (-).
	*Dashes are preferred.*

### Correct file names

- `index.html`
- `general.css`
- `my-website`
- `logo-2.png`

### Incorrect file names

- `Index.html`
- `general.CSS`
- `My Website`
- `logo 2.png`

---

## Folder structure

```
website/
 |- img/
 |- css/
     |- general.css
 |- js/
 |- index.html
```

---

## Indentation

### HTML

All nested elements should be indented with 1 tab.

#### Correct HTML indentation

```html
<body>
	<div>
		<h1>My Heading</h1>
		<p>Lots of paragraph content.</p>
	</div>
</body>
```

### CSS

All properties should be indented with 1 tab.

#### Correct CSS indentation

```css
body {
	background-color: #ccc;
	font-size: 100%;
	font-family: sans-serif;
}
```
