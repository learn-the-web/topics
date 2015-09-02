---
group: web-dev-4
playlist:
download: https://github.com/acgd-learn-the-web/video-audio-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/video-audio-code
---

Video is extremely popular on the web, using up the majority of total bandwidth consumed.

---

## Video on the web

Historically video was difficult to do on the web: you had to provide multiple versions of the video in different formats, QuickTime, RealPlayer, Flash, etc. Flash kinda won for a while and with the advent of YouTube most video on the web was played with Flash.

HTML added a new tag, the `<video>` tag that was to remove the need for having so many different plugins and video formats. With mobile devices not supporting Flash, native video started to win.

---

## Video formats

Unfortunately, for many years we had a video format conflict, some browsers didn’t want to pay exorbitant amounts of money for [MPEG LA](https://en.wikipedia.org/wiki/MPEG_LA)’s H.264 codec and other codecs were used, including [OGG](https://en.wikipedia.org/wiki/Ogg) and [WebM](http://www.webmproject.org/).

H.264 became the dominant format anyways because it was hardware accelerated on mobile devices. Most browsers now support H.264, but many vendors are working together to come up with a patent unencumbered video codec specifically targeted at the web.

So, the benefit to us is that we really only need to provide a `.mp4` encoded in H.264 to support most browsers.

**[You can see the H.264 browser support on Can I Use.](http://caniuse.com/#feat=mpeg4)**

### Exporting from After Effects

---

## The video tag

After you have your video compressed in the right format, it’s really easy to embed it onto your website.

There are two tags we need to embed video on our website:

- `<video>` — the wrapper, with attributes to adjust functionality.
- `<source>` — used to present a video format.

A simple example of embedding a video on a website looks like this:

```html
<video src="video/dinos.mp4"></video>
```

In between the open and close `<video>` tags, you should put some fallback content, kind of like the `alt` attribute on images.

```html
<video src="video/dinos.mp4">
  Dinosaur frolicking in the tall grass.
</video>
```

If you wanted to support more older browsers with different formats you can use multiple `<source>` tags:

```html
<video>
  <!-- Notice the `type` attribute to help the browser determine what video to play -->
  <source src="video/dinos.mp4" type="video/mp4">
  <source src="video/dinos.webm" type="video/webm">
  <source src="video/dinos.ogv" type="video/ogg">
</video>
```

### Controls

By default, there are no playback controls on a video, we need to tell the browser to add those with the `controls` attribute.

```html
<video src="video/dinos.mp4" controls>
  Dinosaur frolicking in the tall grass.
</video>
```

The browser will then present its default set of player controls—that you cannot style.

#### Video players

If you want more access to style the controls of the video player try using a Javascript video library, or see about [making your own controls with Javascript](#using-javascript-to-control-video).

- [MediaElement.js](http://mediaelementjs.com/)
- [Video.js](http://www.videojs.com/)
- [SublimeVideo](http://www.sublimevideo.net/)
- [HTML5 Video Player Comparison](http://praegnanz.de/html5video/)

### Poster

The poster attribute allows you to specify an image that will be displayed to the user before they start playing the video. It can be in any format the browser supports, but likely you want to use JPG or PNG.

```html
<video src="video/dinos.mp4" controls poster="img/dinos-title-screen.jpg">
  Dinosaur frolicking in the tall grass.
</video>
```

### Auto play

There is an `autoplay` attribute you can use on the video tag, it will automatically download and play the video.

Try to avoid auto playing videos—especially videos with sound. Some devices don’t even allow auto play, they require a user interaction to start a video.

```html
<!-- If you must auto play, make sure to add the `muted` attribute to avoid auto playing sounds. -->
<video autoplay muted>

</video>
```

### Adding tracks to video

### Specifying playback range

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

1. Compressing formats
2. Video tag
3. Embed containers
4. Adding tracks to video
5. Using Javascript to control video
6. Javascript hover to play video
7. Hosting off GitHub
8. Audio tag

## Supplemental links

- [Wikipedia: HTML5 video](https://en.wikipedia.org/wiki/HTML5_video)
- [MDN: Using HTML5 audio and video](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML5_audio_and_video)
- [HTML5 Video](http://www.html5rocks.com/en/tutorials/video/basics/)
- [W3C: Media Fragments](http://www.w3.org/TR/media-frags/)
- [Dive Into HTML5: Video](http://diveintohtml5.info/video.html)
