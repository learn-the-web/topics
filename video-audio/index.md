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

### Exporting from Adobe

You can use the Adobe Media Encoder to get your videos out of After Effects or Premiere Pro.

![](ame.jpg)

You want to output an HD 1080p H.264 video, in Adobe Media Encoder, after adding your source, choose the format and preset:

1. Format: “**H.264**”.
2. Preset: “**Vimeo 1080p HD**” or “YouTube 1080p HD”.
  *The regular “HD 1080p 29.97” should also work but may create larger file sizes.*

After the video file is created you should be left with a `.mp4` file, that’s what you need for your website.

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

### Fallback for video

In between the open and close `<video>` tags, you should put some fallback content, kind of like the `alt` attribute on images.

```html
<video src="video/dinos.mp4">
  Dinosaur frolicking in the tall grass.
</video>
```

### Multiple formats

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

*If you must auto play your video make sure to mute the sound with the `muted` attribute.*

```html
<!-- If you must auto play, make sure to add the `muted` attribute to avoid auto playing sounds. -->
<video autoplay muted>

</video>
```

### Specifying playback range

When writing in the `src` attribute of a video you can choose where the video should start and end.

We just need to add a hash onto the URL for the browser to register the range.

```html
<video src="video/dinos.mp4#t=5,20">
  Dinosaur frolicking in the tall grass.
</video>
```

The format of the hash follows this convention:

```
#t=[starttime],[endtime]
```

Some examples:

- `#t=10,20` — start at 10 seconds, end at 20 seconds.
- `#t=,40` — start at the beginning, play until 40 seconds.
- `#t=60` — start at 60 seconds, play to the end.

You can even specify the time in `hours:minutes:seconds`:

- `#t=,2:58:00` — start at the beginning, play until 2 hours, 58 minutes in.

---

## Responsive video

You’ll most likely want to make your video flexible and scale with the dimensions of your website.

**[☛ The best way to make your video responsive is to use embed containers.](/topics/modules/)**

If your video is in the standard aspect ratio for HD of 16 by 9, your HTML will look something like this.

```html
<div class="embed embed--16by9">
  <video class="embed__item" src="video/dinos.mp4">
    Dinosaur frolicking in the tall grass.
  </video>
</div>
```

And the CSS will look something like this:

```css
.embed {
  margin-left: 0;
  margin-right: 0;
  position: relative;
  width: 100%;
}

.embed--16by9 {
  padding-top: 56.25%;
}

.embed__item {
  height: 100%;
  left: 0;
  position: absolute;
  top: 0;
  width: 100%;
}
```

Using the above HTML & CSS will allow your video to scale while still maintaining the proper aspect ratio.

---

## Adding captions & subtitles to video

Tracks and the `<track>` tag are a standard way to provide subtitles, captions, screen reader descriptions, chapters and more for your video.

We just need to add a `<track>` element to the `<video>` tag that points to the appropriate `.vtt` file:

```html
<video src="video/dinos.mp4">
  <track src="video/subtitles.vtt" kind="subtitles" srclang="en" label="English">
  Dinosaur frolicking in the tall grass.
</video>
```

There are a few important attributes to look at:

- `src="…"` — is a URL that points the text file for this track.
- `kind="…"` — what kind of track it is: `subtitles`, `captions`, `descriptions`, `chapters` or `metadata`.
- `srclang="…"` — the language of the content in the track.
- `label="…"` — what the user will see in the interface describing this track.

### Subtitle tracks

Subtitles are used to add transcriptions or translations to the video. They are time-based so that specific words show on the screen in time with the video.

All the tracks use the [WebVTT](http://dev.w3.org/html5/webvtt/) format, an open format for describing this type of content.

#### WebVTT

A WebVTT file is just a plain text file that you can create in your text editor—make sure to use the `.vtt` file extension when you save it.

Here’s a basic example for a subtitle track:

```vtt
WEBVTT

1
00:00:01.000 --> 00:00:10.000
Hey, how’s it going?

2
00:00:15.000 --> 00:00:20.000
Thing’s are good.
How you doin’?
```

You’ll notice a few things:

- The first line in the file must always be `WEBVTT`.
- You can add an optional heading to each entry, like `1` above.
- Next is the time code: `start --> end`.
  It’s in the format of `hours:minutes:seconds.milliseconds`, but the hours are optional.
- After the time code is the text to display, it can be written on multiple lines, but often it’s better to let the device break the lines where appropriate.

#### Styling tracks

It’s possible to style the tracks, especially subtitles and captions. Try to avoid doing too much style changes from the defaults.

Some of the basic things you can change are the following:

- `<b>` — to add bold text.
- `<i>` — to add italic text.
- `<u>` — to add underlined text.
- `<c.my-class>` — to add a class.

Some examples:

```vtt
WEBVTT

1
00:00:01.000 --> 00:00:10.000
Curse your <i>sudden</i> but <b>inevitable</b> betrayal.

2
00:00:15.000 --> 00:00:20.000
I’ve got a <c.super-bad>bad</c> feeling about this.
```

*You could then use the `.super-bad` class in CSS to style the word.*

#### Denoting the voice of the speaker

Inside the caption and subtitle tracks you can denote the voice of the person speaking. There are a few benefits to marking of the name of the voice:

1. The name of the person will be added to the display.
2. It can be read out by screen readers.
3. You can style it so each person has a different colour, etc.

Use the `<v …>` tag to denote a voice, like this:

```vtt
WEBVTT

1
00:00:01.000 --> 00:00:10.000
<v Long Neck>Hey, how’s it going?</v>

2
00:00:15.000 --> 00:00:20.000
<v Horn Head>Thing’s are good.
How you doin’?</v>
```

### Chapter tracks

Chapters allow users to jump to different sections within the video. Each chapter can be labeled however you’d like.

Here’s an example WebVTT file for chapters:

```vtt
WEBVTT

Chapter 1
00:00:00.000 --> 00:10:00.000
Dinosuars frolicking in space
```

This chapter would last from the beginning to exactly 10 minutes into the video.

**Links**

- [HTML5 Doctor: Video Subtitling and WebVTT](http://html5doctor.com/video-subtitling-and-webvtt/)
- [Getting Started With the Track Element](http://www.html5rocks.com/en/tutorials/track/basics/)
- [Wikipedia: WebVTT](https://en.wikipedia.org/wiki/WebVTT)
- [W3C: WebVTT](http://dev.w3.org/html5/webvtt/)
- [Converting SRT files to WebVTT files](http://www.webvtt.org/)

---

## Using Javascript to control video

### Javascript hover to play video

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

## Video list

1. Video & audio: video formats
2. Video & audio: video tag
3. Video & audio: responsive video
4. Video & audio: adding tracks to video
5. Video & audio: using Javascript to control video
6. Video & audio: Javascript hover to play video
7. Video & audio: hosting off GitHub
8. Video & audio: audio tag

## Supplemental links

- [Wikipedia: HTML5 video](https://en.wikipedia.org/wiki/HTML5_video)
- [MDN: Using HTML5 audio and video](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML5_audio_and_video)
- [HTML5 Video](http://www.html5rocks.com/en/tutorials/video/basics/)
- [W3C: Media Fragments](http://www.w3.org/TR/media-frags/)
- [Dive Into HTML5: Video](http://diveintohtml5.info/video.html)
