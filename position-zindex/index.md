---
group: web-dev-1
playlist: PLWjCJDeWfDdfWFmcHzFqGxGzzsx_8MPPP
download: https://github.com/acgd-learn-the-web/position-zindex-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/position-zindex-code
---

Position allows us to move elements around on the screen and bypass the browser’s flow.

*If possible use the browser’s flow before trying to manipulate elements with position.*

---

## Position

The `position` property has a few different values, each doing something slightly different to the element in relation to the flow of the browser:

- `static` — the default, what all elements are before changing the position
- `relative` — slight adjustments within the flow & coordinate system reset
- `absolute` — complete removal from the flow, movement with the coordinate system
- `fixed` — complete removal from the flow, attached to the window, doesn’t move when the browser scrolls

![](static-default.png)

```html
<div class="blue">…</div>
<div class="purple">…</div>
<div class="green">…</div>
```

### Absolute

Position `absolute` completely removes the element from the flow, allowing all other boxes to fill in the space.

![](absolute.png)

```css
.purple {
	position: absolute;
}
```

*Notice how the `.green` element jumps up behind the `.purple` box.*

#### Width collapsing

When an element is set to `position: absolute` its `width` will collapse to be as narrow as the content needs—just like `float`.

So, often when using `absolute` it’s necessary to add a `width` to the element.

#### Coordinate system

When using `position: absolute`, the primary reason is to be able to position something using the coordinate system. The coordinate system is based on the following properties:

- `top` — move the element down from the top, can use negative numbers
- `bottom` — move the element up from the bottom, can use negative numbers
- `left` — move the element in from the left, can use negative numbers
- `right` — move the element in from the right, can use negative numbers

![](coordinates.png)

The only time we want to specify opposing coordinates, like `top` & `bottom`, at the same time is if we want to stretch the element to fill some space.

#### Changing the coordinate system with relative

The default coordinate system is based on the `body`—so any positioning we do will always be in relation to the edges of the `body` element.

![](against-body.png)

```html
<div class="grey-border">
	<div class="purple">…</div>
</div>
```

```css
.purple {
	position: absolute;
	right: 0;
	bottom: 0;
}
```

We can reset the coordinate system by adding `position: relative` to a parent of the element. After setting `relative`, a new positioning context is created, and the coordinates will automatically be positioned against the parent element instead.

![](against-relative.png)

```css
.grey-border {
	position: relative;
}
```

### Relative

Though `relative` creates a new positioning context, reseting the coordinate system, it also allows the element to take up space in the flow while adjusting its position slightly with the coordinates.

![](relative.png)

```html
<div class="blue">…</div>
<div class="purple">…</div>
<div class="green">…</div>
```

```css
.purple {
	position: relative;
	top: 10px;
	right: 10px;
}
```

### Fixed

Completely removes the box from the flow allowing all other boxes fill the space.

But `position: fixed` always positions against the window and does not move when the user scrolls.

```css
nav {
	position: fixed;
	top: 0;
	width: 100%;
}
```

*Position fixed doesn’t work very well in many situations—espeically mobile devices—so be careful when using it.*

---

## Z-index

As soon as an element has a `position` set on it we can control the layering using `z-index`.

*`z-index` doesn’t work on elements that are `position: static`, the default.*

The default stacking order for `position: absolute` elements is: *the further down the page the HTML is, the higher up, or closer to the viewer, the element will appear.*

![](default-stacking.png)

```html
<div class="blue">…</div>
<div class="purple">…</div>
```

```css
.blue {
	position: absolute;
	top: 0;
	left: 20%;
}

.purple {
	position: absolute;
	top: 0;
	left: 30%;
}
```

By adding `z-index` to the elements we can control their layering.

The `z-index` is a number, with no unit, that controls the layer. The higher the number, the closer to the viewer. The number only needs to be as high as how many other elements there are in the context.

![](z-index.png)

```css
.purple {
	z-index: 2;
}
```

---

## Video list

1. [Position: introduction](https://www.youtube.com/watch?v=jVWnfwOZPDI&list=PLWjCJDeWfDdfWFmcHzFqGxGzzsx_8MPPP&index=1)
2. [Position: polariod](https://www.youtube.com/watch?v=kNJuF4aVHEA&list=PLWjCJDeWfDdfWFmcHzFqGxGzzsx_8MPPP&index=2)
3. [Posiiton: planet list](https://www.youtube.com/watch?v=LU3BkaRVf_8&list=PLWjCJDeWfDdfWFmcHzFqGxGzzsx_8MPPP&index=3)
4. [Position: layering with z-index](https://www.youtube.com/watch?v=6VK4KLW0gS8&list=PLWjCJDeWfDdfWFmcHzFqGxGzzsx_8MPPP&index=4)
5. [Position: hero banner](https://www.youtube.com/watch?v=3MpEnd_rRuY&list=PLWjCJDeWfDdfWFmcHzFqGxGzzsx_8MPPP&index=5)
6. [Position: position and float](https://www.youtube.com/watch?v=wydLbIagYsI&list=PLWjCJDeWfDdfWFmcHzFqGxGzzsx_8MPPP&index=6)

## Supplemental links

- [MDN: position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
- [MDN: z-index](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index)
- [Learn Layout](http://learnlayout.com/)
- [What You May Not Know About the Z-Index Property](http://webdesign.tutsplus.com/tutorials/what-you-may-not-know-about-the-z-index-property--webdesign-16892)
