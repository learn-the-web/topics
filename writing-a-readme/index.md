---
group: web-dev-4
---

The readme is one of the most important files in a open project, helping users understand the purpose, whether/how they can use it, and documentation.

---

## README.md

*Yes, uppercase. ̛I know it breaks all our naming convention. It’s a bit shouty but a historical convention.*

---

## Other files to consider including

When creating a public-facing or open source project, beyond the readme, there’s a few other files you should consider adding.

## License

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
- A version number for each release and whether the project follows [Semantic Versioning] or not
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

## Supplemental links

- [Wikipedia: Readme](https://en.wikipedia.org/wiki/README)
- [README.md template](https://gist.github.com/jxson/1784669)
- [A Beginner’s Guide to Creating a README](https://changelog.com/a-beginners-guide-to-creating-a-readme/)
- [Readme Driven Development](http://tom.preston-werner.com/2010/08/23/readme-driven-development.html)
- [Shields.io](http://shields.io/)
