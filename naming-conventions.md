---
title: "Naming conventions"
tags: "naming conventions lower case dashes no spaces underscore folders files structure"
desc: "Writing the proper file name for consistency on the web."
cheatsheet: naming-paths-cheat-sheet
extra_practice:
  activities:
    - title: "Naming Conventioneer"
      url: "naming-conventioneer"
---

When coding websites there’s a restriction on how we must name our files and folders.

---

## Rules

When it comes to the web we have a few very specific rules for naming *every single file and folder* in our website.

1. **All lowercase** — all files & folder must us only lowercase characters.
  This includes extensions, like .jpg, .png, etc.

2. **No spaces** — no spaces allowed anywhere in file & folder names.
  Be careful their are spaces hidden at the end, after the extension.
  Use a dash (`-`) to separate words.

3. **Only letters, numbers & dashes** — use dashes (`-`) to separate words.
  The only exception is the dot (`.`) before extensions.
  Underscores (`_`) are also acceptable, but not preferable.

*These rules also apply to domains for your website.*

---

## Why

The reasons for the above rules are purely technical—they aren’t about personal preference.

### Why lowercase?

**Because different operating systems treat capitalization differently.**

When developing websites we mostly use Mac OS or Windows for development. These two operating systems are “case insensitive”, meaning they ignore capital letters and treat them the same as lowercase letters.

On Mac and Windows, the following files are all identical:

```
photo.jpg
photo.JPG
Photo.jpg
Photo.JPG
pHoTo.JPG
```

From the operating systems’ point of view, those are all the same file and you could not have two of those files in the same location, the OS wouldn’t allow it.

But most often we host websites on Linux servers. Linux is a “case sensitive” operating system. In Linux-based environments all those files listed above are completely different and could all exist in the same folder.

This creates a slight annoyance, because if you accidentally link to file in your code with a lowercase letter, but in the system it’s uppercase, Mac and Windows would be okay with it and work, but Linux would not. On your local computer you wouldn’t see a difference, but as soon as you launched your website things would break.

So, it’s much easier to standardize on lowercase, we then don’t run into any unnecessary problems.

### Why no spaces?

**Because URLs cannot have spaces in them.**

URLs in browsers just cannot have spaces in them, they must be escaped with a character entity like this: `%20`.

So unless you want to go around writing `%20` everywhere you link to files with spaces—don’t use spaces.

### Why separate words with dashes?

**Because, for search engines, dashes are word separators and underscores are word connectors.**

If you’d like to separate words (which is a good idea for clarity), instead of a space, use a dash (`-`). Dashes are preferable to underscores because search engines treat underscores as word connectors, where dashes are treated was word separators.

Some examples of how dashes vs. underscores work:

- `photo-1.jpg` — Using a dash as a word separator.
- `meat-eating-dinosaurs.html` — Each word will be separated for searching: “meat”, “eating” & “dinosaurs”.
- `big_t_rex_dino` — Search engines will show results for exactly “big_t_rex_dino”, but not for “dino” or “t-rex” or “big”.

### Why only numbers letters and dashes?

**Because URLs use a limited set of characters.**

URLs in browsers use a limited set of ASCII characters, so those are the only characters we should be using.

Many browsers do support other characters that aren’t ASCII, but you many run into problems, so unless you need to, just use the basic set.

Also, domains can be in other languages, with other characters, they don’t have to be English ASCII characters, but internally browsers and the DNS system just maps them to a ASCII only system called Punycode. As an example, the domain `Bücher.ch` (a German word, with a Swiss TLD), is translated into this: `xn--bcher-kva.ch`.

**Links**

- [Wikipedia: List of allowed URL characters](https://en.wikipedia.org/wiki/Uniform_resource_locator#List_of_allowed_URL_characters)
- [Wikipedia: Internationalized domain name](https://en.wikipedia.org/wiki/Internationalized_domain_name)

---

## Exceptions

As with all rules there are exceptions. When it comes to files & folders there are a few that—by convention—break our rules.

- `README.md` — The description of your project; always all caps, with or without an extension.
  Sometimes you may also see `CONTRIBUTING.md`, `CHANGELOG.md` and a few others.
  [☛ Learn more about Readmes](/topics/writing-a-readme/)
- `LICENSE` — The license file for your project; always all caps, rarely an extension.
  [☛ Learn more about Licenses](/topics/licenses-copyright/)
- `CNAME` — The file used by GitHub to associate a custom domain to your website; always all caps, no extension.
  [☛ Learn more about Custom domains](/topics/domains/)

As mentioned above, domains can also use non-English ASCII characters, but those get mapped back to the standard character set internally.
