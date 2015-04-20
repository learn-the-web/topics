# Installing Jekyll on Windows

1. Download a portable, Windows version of Jekyll from [Madhur Ahuja’s Dropbox](https://www.dropbox.com/sh/40l6mgbl1ce2kej/lF6ykQxt9d)
2. Unzip the folder and put it directly in your `C:\ Drive`
3. Make sure to name the folder `Jekyll`
4. Go to `Control Panel`, search for `System` and open it
5. Edit `System Environment Variables`
6. Scroll through the list and find `Path` and edit it
7. Go to the very end of the text field and paste this:

```
;C:\Jekyll\ruby\bin;C:\Jekyll\devkit\bin;C:\Jekyll\git\bin;C:\Jekyll\Python\App;C:\Jekyll\PortableJekyll\devkit\mingw\bin
```

And it *should* work. If you’d like to test open *Command Prompt* and type this:

```
jekyll -v
```

You should see output that looks similar to this:

```
jekyll 1.3.1
```

---

- [Read Madhur Ahuja’s Blog Post](http://www.madhur.co.in/blog/2013/07/20/buildportablejekyll.html)
