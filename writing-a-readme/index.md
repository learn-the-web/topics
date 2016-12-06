---
playlist: PLWjCJDeWfDdeFtHCKhhjdgiYFdPT8mvh_
download: https://github.com/acgd-learn-the-web/writing-a-readme-samples/archive/master.zip
github: https://github.com/acgd-learn-the-web/writing-a-readme-samples
---

The readme is one of the most important files in a open project, helping users understand the purpose, whether/how they can use it, and documentation.

---

## README.md

*Yes, uppercase. ̛I know it breaks all our naming conventions. It’s a bit shouty but a historical convention because uppercase letters are sorted to the top of file lists.*

The readme file is the go-to file for any open source and public project: a place to give people an overview of all the important information about the project.

Readmes are almost always plain-text files, and **[☛ Markdown](/topics/markdown/)** has become a very popular formatting system for the files to keep them organized.

### What to include

- **Title** — at the very top, in a heading, try to make it descriptive and unique
- **Version** — the current version of your project, preferably using [Semantic versioning](#semantic-versioning)
- **Description & motivation** — share your vision, *why* you made it, its purpose
- **Installation instructions** — how to get it up and running, dependencies, examples, etc.
- **Use instructions, quick start documentation & troubleshooting** — descriptive examples *with code*, obvious, concise, common problems and gotchas, etc.
- **Demos** — links to live examples if possible
- **Contributors & how to get involved** — who is involved & contact information, how others can contribute, report bugs, feature requests
- **License** — copyright and licensing information, link to license file, bibliographic entries for other sources used, etc.

### Semantic versioning

When adding a version number to your project there’s a common system that many projects follow—using three numbers separated by periods.

*Some examples:*

```
1.0.0
0.10.4
4.1.8
1.7.24
```

Each number has a specific meaning and they break down like this: `MAJOR.MINOR.PATCH`:

- *Patch* — increment this number when you make small, backwards-compatible changes, bug fixes
- *Minor* — increment this number when you add something new, that’s still backwards-compatible
  Changing this number resets the Patch number to 0.
- *Major* — increment this number when you add something that will break everything else, backwards-incompatible changes
  Changing this number resets the Minor and Patch numbers to 0.

*The numbers aren’t like math decimals, when you hit “10” it doesn’t increase the previous number.*

#### Version number matching

Sometimes you’ll see version numbers starting with a tilde or a caret. Specifically when referencing version of other code used in your applications (dependencies).

The two characters denote what versions are compatible with your project.

- **^** — caret, any backwards compatible change, MINOR or PATCH version changes, e.g. 2.\*.\*
- **~** — tilde, only bug fix changes, PATCH version updates, e.g. 2.1.\*

**Links**

- [Semantic Versioning](http://semver.org/)
- [Semver explained - why there’s a caret (^) in my package.json?](http://bytearcher.com/articles/semver-explained-why-theres-a-caret-in-my-package-json/)

---

## Other files to consider including

When creating a public-facing or open source project, beyond the readme, there’s a few other files you should consider adding.

### License

`LICENSE`, `LICENSE.md`

It’s extremely important to put license and copyright information at the bottom of your readme file.

But, if you’re using an OS license you most likely want to include that in your project in a separate file, with the completely license text and copyright notice.

**[☛ Learn more about licenses & copyrights.](/topics/licenses-copyright/)**

### Contribution details

`CONTRIBUTING.md`

A contributing file covers how people should get involved in your project, what you’re looking for, the process, channels, etc.

Some things to include in your contributing file:

- List of core team members and contact information
- How to watch and learn about the development: mailing list, blog, IRC, etc.
- How to submit issues, problems, bugs, etc.
- How to submit a new feature, a patch, a pull request, etc.
- Coding & committing style and guidelines
- How to submit a translation or documentation change
- How non developers can contribute: communication, newsletters, Q&A, blog, videos, etc.

#### Code of conduct

It’s extremely important to be inclusive with your project, so having a clear code of conduct is helpful. **Just having a code of conduct isn’t enough—being inclusive and sticking to it and backing up people who were wronged is what really matters.**

*From Contributor Covenant:*

> Open Source has always been a foundation of the Internet, and with the advent of social open source networks this is more true than ever. But open source projects suffer from a startling lack of diversity of participants, including women, people of color, and other minority populations.

> Part of this problem lies with the projects themselves. Insensitive language, thoughtless use of pronouns, projects with sexualized or culturally inappropriate names, and side effects of the pervasive cult of meritocracy make contributing to open source a daunting prospect for many people.

**Links**

- [Contribute.md](http://contribute.md/)
- [Contributor Covenant](http://contributor-covenant.org/)
- [Open Code of Conduct](http://todogroup.org/opencodeofconduct/)

### Change logs

`CHANGELOG`, `CHANGELOG.md`

A change log is a file that lists out everything that has changed in the code for each version released. It helps people understand what has changed in each version, new features, and whether they need to update their code to support the newer version.

*Always write your change log for humans—not machines.*

Somethings consider adding to your change log:

- Reverse chronological order of versions
- Each version should have a date written in ISO 8601 standard: YYYY-MM-DD
- A version number for each release and whether the project follows [Semantic Versioning](#semantic-versioning) or not
- Links to important sections an out to issues, documentation, etc.
- Each version entry should contain this information:
  - “Added” — new features added to the project
  - “Changed” — existing functionality that is different from the earlier version
  - “Deprecated” — features that exist but should no longer be used
  - “Removed” — any deprecated features removed in this release
  - “Fixed” — any bugs that have been fixed
  - “Security” — any issues related to security or what new security features exist

**Links**

- **[Keep a CHANGELOG](http://keepachangelog.com/)**

---

## Video list

1. [Writing a readme: writing a readme](https://www.youtube.com/watch?v=RZ5vduluea4&index=1&list=PLWjCJDeWfDdeFtHCKhhjdgiYFdPT8mvh_)
2. [Writing a readme: adding a license](https://www.youtube.com/watch?v=gJZGLZSzP_I&index=2&list=PLWjCJDeWfDdeFtHCKhhjdgiYFdPT8mvh_)
3. [Writing a readme: creating a change log](https://www.youtube.com/watch?v=y6hVxxi-DnY&index=3&list=PLWjCJDeWfDdeFtHCKhhjdgiYFdPT8mvh_)

## Supplemental links

- **[18F’s Guide to making READMEs readable](https://pages.18f.gov/open-source-guide/making-readmes-readable/)**
- [Wikipedia: Readme](https://en.wikipedia.org/wiki/README)
- [README.md template](https://gist.github.com/jxson/1784669)
- [A Beginner’s Guide to Creating a README](https://changelog.com/a-beginners-guide-to-creating-a-readme/)
- [Readme Driven Development](http://tom.preston-werner.com/2010/08/23/readme-driven-development.html)
- [Shields.io](http://shields.io/)
- [The Twelve-Factor App](http://12factor.net/)
