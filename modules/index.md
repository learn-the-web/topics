---
group: web-dev-2
playlist: PLWjCJDeWfDddIWwftJxBqtHpw8CbFMXsa
download: https://github.com/acgd-learn-the-web/modules-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/modules-code
---

Thinking modularly in CSS allows us to create more reusable CSS.

---

## Examples

- [List group](list-group.html): vertical & horizontal
- [Buttons](buttons.html): small, medium, large, alternative, [buttons + modular typography](buttons-modular-type.html)
- [Icons](icons.html): different sizes, stacked, inline, image replacement
- [Media object](media-object.html): flexible image size, embeddable, with list group, stacked, reversed
- [Embed containers](embed.html): for flexible images and videos, with specific aspect ratios—to prevent layout reflow after the image loads

*The `common.css` file used in the examples and videos could be replaced by your modular typography `typography.css` file for better results.*

---

## Naming conventions

There are a couple major naming conventions for modular CSS that help clarify the intent of our classes and help us visualize the HTML by ust looking at the CSS classes.

- [BEM](http://bem.info/)
- [SMACSS](http://smacss.com/)

Part of what we learned today comes directly from SMACSS: the icon naming conventions.

BEM takes naming a little further by using double underscores or double hyphens to represent certain ideas.

- [Getting Your Head Around BEM Syntax](http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)

```html
<div class="media media--highlighted">
	<div class="media__img"></div>
	<div class="media__body"></div>
</div>
```

1. Name your component with a descriptive phrase, e.g. `media`
2. Any classes that modify an original, base class, are separated with hyphens, e.g. `media--highlighted`
3. Any classes that represent pieces that are inside of the original class, or sub-components, are separated with underscores, e.g. `media__body`

I find it helpful to remember that when using **under**scores the element is **under** the original component.

---

## Video list

1. [Modules: list group](https://www.youtube.com/watch?v=Kcd1742iCVA&list=PLWjCJDeWfDddIWwftJxBqtHpw8CbFMXsa&index=1)
2. [Modules: buttons](https://www.youtube.com/watch?v=u4yYGmI2-Qk&list=PLWjCJDeWfDddIWwftJxBqtHpw8CbFMXsa&index=2)
3. [Modules: making modular icons](https://www.youtube.com/watch?v=s8198ThMOgA&list=PLWjCJDeWfDddIWwftJxBqtHpw8CbFMXsa&index=6)
4. [Modules: combining the icons and the list group](https://www.youtube.com/watch?v=zfUErXraYCc&list=PLWjCJDeWfDddIWwftJxBqtHpw8CbFMXsa&index=7)
5. [Modules: icon image replacement](https://www.youtube.com/watch?v=bv6OQ6X5xWY&list=PLWjCJDeWfDddIWwftJxBqtHpw8CbFMXsa&index=8)
6. [Modules: media object](https://www.youtube.com/watch?v=bE0VpK1SjUc&list=PLWjCJDeWfDddIWwftJxBqtHpw8CbFMXsa&index=3)
7. [Modules: combining the media object and the list group](https://www.youtube.com/watch?v=V4QQFVa2Dok&list=PLWjCJDeWfDddIWwftJxBqtHpw8CbFMXsa&index=4)
8. [Modules: media object alternatives](https://www.youtube.com/watch?v=TTTrGPlIBJ8&list=PLWjCJDeWfDddIWwftJxBqtHpw8CbFMXsa&index=5)
9. [Modules: embed containers](https://www.youtube.com/watch?v=UQLq8w_gOv0&list=PLWjCJDeWfDddIWwftJxBqtHpw8CbFMXsa&index=10)
10. [Modules: embedding videos responsively](https://www.youtube.com/watch?v=noEcV1AFY-g&list=PLWjCJDeWfDddIWwftJxBqtHpw8CbFMXsa&index=11)
11. [Modules: embed containers with figures](https://www.youtube.com/watch?v=9tbM8i9K6lw&list=PLWjCJDeWfDddIWwftJxBqtHpw8CbFMXsa&index=12)
12. [Modules: combining buttons with modular typography](https://www.youtube.com/watch?v=z01-pDAd0HA&list=PLWjCJDeWfDddIWwftJxBqtHpw8CbFMXsa&index=13)

## Supplemental links

- [OOCSS](https://github.com/stubbornella/oocss/wiki)
- [An Introduction to OOCSS](http://coding.smashingmagazine.com/2011/12/12/an-introduction-to-object-oriented-css-oocss/)
- [The Flag Object](http://csswizardry.com/2013/05/the-flag-object/)
- [CSS Wizardry: CSS Guidelines](https://github.com/csswizardry/CSS-Guidelines)
- [Responsive Images: How to Prevent Reflow](http://andmag.se/2012/10/responsive-images-how-to-prevent-reflow/)
