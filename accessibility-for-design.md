---
title: "Accessibility for design"
tags: "accessibility humans impairments visual mobility dexterity auditory cognitive color blindness memory deafness transcript captions wai aria landmark roles skip links focus styles tools total validator screen readers VoiceOver braille"
desc: "Making our website design work well for every human being regardless of their abilities."
---

## Keyboard focus styles

Not everybody is capable of using a mouse, or even chooses not to use a mouse. But they still need to be able to navigate your website—and keep their position.

Focus styles highlight the currently selected element on screen so it’s recognizable as keyboard focused control.

_It’s important to not remove the keyboard focus rectangle from links, but it can be styled for better contrast or to match your website._

```css
a:focus {
  outline: 3px solid #000;
}
```

_But don’t ever write `outline: none;` on the `:focus` state—it’s an extremely important feature for keyboard users._

---

## Skip links

It’s a good idea to add skip links to a website for jumping over the navigation to the main content. Or adding a skip link to jump from the bottom to the top of the website.

Skip links are just standard internal links that jump down to a specific point of a page.

```html
<a href="#main">Jump to main content</a>

⋮

<main role="main" id="main"></main>
```

To help make the content focusable more easily it’s also helpful at add `tabindex` to the skip link element:

```html
<main role="main" id="main" tabindex="0"></main>
```

Most often designers like to hide them but they must be hidden in an accessible manner. Hidden by default but when focused, shown again.

```css
.skip-links a {
  position: absolute;
  top: -3em;
}

.skip-links a:focus {
  top: 0;
}
```

---

## Video list

1. [Accessibility: skip links](https://www.youtube.com/watch?v=UnEItq289lU&list=PLWjCJDeWfDdcEtSnqq_iGLKGA_H_3o3y7&index=5)
1. [Accessibility: tools to help find issues](https://www.youtube.com/watch?v=xpqPctbDhnc&list=PLWjCJDeWfDdcEtSnqq_iGLKGA_H_3o3y7&index=6)
