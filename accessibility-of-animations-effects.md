---
title: "Accessibility of animations & effects"
tags: "accessibility animations effects prefers reduced motion humans impairments visual mobility dexterity auditory cognitive color blindness memory deafness transcript captions wai aria landmark roles skip links focus styles tools total validator screen readers VoiceOver braille"
desc: "Help everyone get the most out of your website by providing the best experience regardless of ability."
playlist: accessibility-of-animation-effects
download: https://github.com/learn-the-web/accessibility-code/archive/master.zip
github: https://github.com/learn-the-web/accessibility-code
---

Animations & effects can really make a web design sing. But they can also be detrimental to lots of people.

Animations and motion can be a distraction. Flashing images can cause seizures. Different levels of contrast are helpful for different people. Even preferences on interface colour scheme help people concentrate & complete their tasks.

We can handle all these things in our design with a little bit of CSS & a little extra design work.

---

## Animated GIFs

**Never use an animated GIF—ever.**

*They cannot be stopped.*

- If there’s too much flashing it could induce seizures
- They could distract users from their task

They are also *huge* files & terrible for performance.

Instead, it’s much better to use a MP4 video. The video can be looped & autoplayed like a GIF. But also paused. And videos are streamed—so they’re much better for performance and bandwidth.

---

## Autoplay

That brings us directly to autoplay. **Don’t autoplay anything on your website.**

- It’s distracting
- It’s bandwidth hogging
- It’s poor accessibility

*Thankfully most browsers have features to prevent autoplay now—which I have enabled.*

---

## CSS media features

There are a few CSS media features we can use to help detect user preferences and adjust our designs accordingly.

### Prefers colour scheme

*Some of you prefer the dark colour scheme—some prefer the light colour scheme.*

To switch you colour scheme on MacOS, go to `System Preferences > General > Appearance`

![](color-scheme.jpg)

In CSS, we can detect the colour scheme by using the `prefers-color-scheme` media query.

```
main {
  background-color: #f2f2f2;
}

@media (prefers-color-scheme: dark) {

  main {
    background-color: #111;
  }

}
```

*In this CSS we start with a light coloured interface. If our users prefers a dark colour, we switch over to that.*

### Prefers reduced motion

*Animations are distracting & annoying to lots of people’s concentration—or cause more serious problems.*

MacOS, and most OSs allow users to change an accesibility setting that says they prefer to have less animations. On MacOS, we can do this in the Accessibility settings.

```
System Preferences > Accessibility > Display > Display
```

![](motion.jpg)

In CSS, we can detect the preference for reduced motion with a media query too:

```css
.ball {
  animation: spin 1s infinite;
}

@media (prefers-reduced-motion) {

  .ball {
    animation: none;
  }

}
```

*With this CSS we detect a preference for reduced motion and just disable the animations on the page.*

### Upcoming preferences

There are some other, newer preferences we’ll be able to detect in the our websites soon:

- `prefers-contrast` — Determine if a high-contrast interface is requested
- `prefers-reduced-transparency` — Determine if a reduced use of transparency is requested

---

## Video list

- [Accessibility of animations & effects: User preferences](https://videos.learntheweb.courses/playlists/accessibility-of-animation-effects/#1-user-prefs)
