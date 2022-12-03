---
title: "Jekyll terminal guide"
tags: "jekyll terminal command line serve watch base url"
desc: "A guide to Jekyll’s terminal commands on your Mac."
playlist: jekyll
video: 5-jekyll-start-stop
---

Jekyll is a command line tool so we have to use the Terminal application on our computer to start, stop, and run Jekyll.

---

## Open folder in Terminal

*This guide assumes you’re running Jekyll on GitHub Pages and that you’ve followed the setup directions here: [**☛ Jekyll installation.**](/topics/jekyll-installation/)*

In the GitHub application, click `Repository > Open in Terminal`.

![](open.jpg)

**Or** press ``Control-` ``.

---

## Run Jekyll

When in Terminal, type the following command:

```bash
bundle exec jekyll serve
```

![](start.jpg)

Jekyll will now be available in your browser at the following URL: **<http://127.0.0.1:4000>**.

**Alternatively you can use: <http://localhost:4000> (`127.0.0.1` & `localhost`) are interchangeable.**

You can see the address Jekyll provides in the Terminal, under the “Server Address” entry:

![](url.jpg)

**Keep this running the whole time you’re working on your Jekyll website.**

---

## Stop Jekyll

In Terminal, you can press the following shortcut key: `Control+C`

![](stop.jpg)

**Or** just quit Terminal.

---

## Video list

- [Jekyll: Starting and stopping](https://videos.learntheweb.courses/playlists/jekyll/#5-jekyll-start-stop)
