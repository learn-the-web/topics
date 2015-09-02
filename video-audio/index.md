---
group: web-dev-4
playlist:
download: https://github.com/acgd-learn-the-web/video-audio-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/video-audio-code
---

Video is extremely popular on the web, using up the majority of total bandwidth consumed.

---

## Video on the web

Historically video was difficult to do on the web: you have to provide multiple versions of the video format, QuickTime, RealPlayer, Flash, etc. Flash kinda won for a while an with the advent of YouTube most video on the web was played with Flash.

HTML added a new tag, the `<video>` tag that was to remove the need for having so many different plugins and video formats. With mobile devices not supporting Flash, native video started to win.

---

## Video formats

Unfortunately, for many years we had a video format conflict, some browsers didn’t want to pay exorbitant amounts of money for MPEG LA’s H.264 codec and other codecs were used, including [OGG](https://en.wikipedia.org/wiki/Ogg) and [WebM](http://www.webmproject.org/).

H.264 became the dominant format anyways because it was hardware accelerated on mobile devices. Most browsers now support H.264, but many vendors are working together to come up with a patent unencumbered video codec specifically targeted at the web.

So, the benefit to us is that we really only need to provide a `.mp4` encoded in H.264 to support most browsers.

**[You can see the H.264 browser support on Can I Use](http://caniuse.com/#feat=mpeg4)**

### Exporting from After Effects

## The video tag

### Controls

#### Video players

- [MediaElement.js](http://mediaelementjs.com/)
- [Video.js](http://www.videojs.com/)
- [SublimeVideo](http://www.sublimevideo.net/)
- [HTML5 Video Player Comparison](http://praegnanz.de/html5video/)

### Poster

### Auto play

There is an `autoplay` attribute you can use on the video tag, it will automatically download and play the video.

Try to avoid auto playing videos—especially videos with sound. Some devices don’t even allow auto play, they require a user interaction to start a video.

```html
<!-- If you must auto play, make sure to add the `muted` attribute to avoid auto playing sounds. -->
<video autoplay muted>

</video>
```

### Adding tracks to video

---

## Embed containers

---

## Using Javascript to control video

### Javascript hover to play video

---

## SD/HD video switch?

---

## Hosting off GitHub

---

## The audio tag

### Audio formats

### Auto play

Using the `autoplay` attribute it is possible to make sounds play automatically on your website. But…

**Don’t auto play sounds. Ever.**

Not only is it extremely annoying, but imagine how frustrating it must be for people who are trying to listen to screen reader when all of a sudden some random sound blurts out.

---

---

## Video list

## Supplemental links

