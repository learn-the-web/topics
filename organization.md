---
title: "Website file organization"
tags: "on off github assets production design content www version control dropbox invision"
desc: "How to organize all the different files associated with websites."
playlist: PLWjCJDeWfDdfJhlnFDLwCu4GZ_2lfuMMx
---

Below is a way to organize your website & production files in a logical manner that’s appropriate for GitHub.

---

## File & folder organization

It’s best to separate the production and design files from the compressed output files that are used on the website.

**Below is how I organize my files—it works for me. That doesn’t mean it’s perfect for you.**

Design and production files should not go inside the GitHub repository, but instead it’s best to put them in Dropbox.

- Git & GitHub don’t support large binary files so we can’t put any Creative Suite files there.
- Putting the Creative Suite files into [Dropbox](#benefits-of-dropbox) & [InVision](#benefits-of-invision) have lots of benefits.
- The Creative Suite files should always be kept because they will need to be changed in the future.
- The files used in a website should be [compressed and smushed for the best performance](../performance/)—and therefore cannot be edited.

![](project.jpg)

First, create a folder that will hold all your project files—name it descriptively.

Inside this folder create 4 more directories: `assets`, `content`, `design`, `production`.

### assets

![](assets.jpg)

*For anything you **didn’t** create:*

- Downloaded icons
- Stock photos
- Web fonts

### content

![](content.jpg)

*For the website’s text-based content:*

- Word documents from clients
- Content inventories
- Information architecture
- Content models

### design

![](design.jpg)

*For design related things you **did** create:*

- Mockups
- Sitemaps
- Personas
- Wireframes
- Research
- Style tiles
- Interviews

### production

![](prod.jpg)

(I’m often lazy and just name this folder `prod`.)

*Extracted**—editable—**files from mockups and designs ready to be used on a website:*

- AI files for SVGs
- PSD files for JPGs & PNGs
- Complete duplicates of files used on a website in their native format

#### Tips for production files

- Make patterns as minimal as possible: only one of the repeated pieces is necessary.
- If there are lots of images that are nearly identical, specifically dimension and theme-wise, put them in one PSD separated onto different layers.
- Make border-image files as small as possible.

**There should be a duplicate of each file in the `www/images` folder—but in it’s compressed format.**

### www

![](www.jpg)

*This is your GitHub repository—it doesn’t necessarily need to be named `www`.*

- HTML
- CSS
- Javascript
- Compressed & smushed images
- If it doesn’t go on GitHub, it doesn’t go in this folder

*Putting the Git repository in Dropbox has nice backup potential (although not necessary if the Git repo is synced to a service like GitHub)—but Dropbox and Git can sometimes conflict.*

#### www/images

![](www-images.jpg)

*The extracted & smushed**—non-editable—**images for the website:*

- Compressed & smushed JPGs
- Compressed & smushed PNGs
- Smushed SVGs
- Can be further organized into sub folders

**There should be a duplicate of each file in the `production` folder—but in it’s original format.**

---

## What goes on/off GitHub

**Files ON GitHub:**

- Anything text-based: HTML, CSS, Javascript, SVG, plain text, Markdown
- Compressed & smushed images: JPGs, PNGs, GIFs

**Files NOT ON GitHub:**

- Adobe Creative Suite files: AI, PSD, INDD, PDF
- Font files: OTF, TTF, WOFF
- Compressed files: ZIP, GZ
- Video & audio: MP4, OGV, M4A, MP3, OGG

*[Consider using a CDN for binary files.](../performance/)*

---

## Version control for design & production files

We version control all our code already with Git & GitHub, but our design files aren’t under version control by default.

We can use a couple of services to version control our big files: Dropbox or Invision.

### Benefits of [Dropbox](https://www.dropbox.com/)

Storing your mockups, design files, and production files in Dropbox has a few benefits:

1. You can easily share those files with other members of your team.
2. You get automatic version control and backups lasting 30 days (unless you upgrade).
3. You can see the files on any device & they can be shared with many online tools.

### Benefits of [InVision](http://www.invisionapp.com/)

Syncing your mockups, design files, and production files to InVision has a few benefits:

1. You can easily share those files and get feedback from your clients.
2. You get automatic version control every time you save the file.

**Links**

- [Design File Syncing](http://blog.invisionapp.com/design-file-syncing/)

---

## Other things to consider

This isn’t a perfect folder structure, but it works for me.

- Maybe create a `ux` folder and separate the UX stuff from graphic design stuff.
- Maybe the `www` folder needs to be in another location to work with a web server or virtual machine.
- What files do your clients need access to?
- Maybe make a folder to sync with your CDN.

---

## Video list

1. [Organizing web files](https://www.youtube.com/watch?v=V3xDoXeq0ic&list=PLWjCJDeWfDdfJhlnFDLwCu4GZ_2lfuMMx&index=1)
