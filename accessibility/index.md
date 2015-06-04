---
group: web-dev-2
playlist: PLWjCJDeWfDdcEtSnqq_iGLKGA_H_3o3y7
download: https://github.com/acgd-learn-the-web/accessibility-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/accessibility-code
checklist: accessibility-checklist
---

The Open Web is an amazingly empowering platform for every human being. It’s our job as web developers to make it work for everyone.

---

## It’s about everyone

**Accessibility is about every human—not just extreme cases.** Sometimes it’s easier to think in terms of extremes because it gives us a goal, but making our website work better for extremes also makes it work better for everybody else.

The great thing about the web and computers is that they empower everybody. *It’s our goal to help every human accomplish what they want on our website, regardless of their physical, mental, or technological capabilities.*

---

## Impairments

Looking at specific impairments helps us narrow in on specific issues and fixing these issues helps our website work for everyone else.

There are lots of different impairments that can affect human beings. **But it’s important thing to remember is that these impairments can be temporary—as an example: a broken arm.**

### Visual

Visual impairments are issues that affect eyes, e.g. blindness, partial or full; colour blindness; cataracts; glaucoma; age; etc.

**Things we can do**

- Allow text to be resized
- Have good contrast in colours
- Test for colour blindness related issues
- Make sure the website works well with screen readers
- Use proper alt attributes

### Mobility and dexterity

Mobility and dexterity impairments primarily affect people’s arms and hands, e.g. missing a hand, limited movement, difficulty with fine control, trouble holding a mouse, termors or shakes, etc.

**Things we can do**

- Recognize and prepare for the fact that not everybody will use a mouse
- Make the website keyboard accessible
- Increase hit areas of links and buttons

### Auditory

Impairments that affect a person’s ability to hear, e.g. deafness, partial deafness, etc.

**Things we can do**

- Provide text captions and subtitles

### Cognitive

Generally considered something that affects a person’s brain, e.g. dyslexia, memory issues, problem solving issues, attention deficits, hyperactivity, reading abilities, etc.

**Things we can do**

- Make it clear where in the website the user is
- Organize your content correctly & use proper headings
- Make the text easily scannable
- Clearly mark links
- Use lots of images and graphics

---

## WAI-ARIA roles & properties

The Accessible Rich Internet Application specification defines whole bunch of roles and attributes that can be assigned to HTML elements to help them be understood.

We may make tabs in HTML with lists and divs, and they may look like tabs, but to accessibility tools like screen readers they’re just lists and divs. ARIA allows us to turn them into functional and understandable tabs with a few extra properties & some Javascript.

**[☛ Check out the tutorial on Javascript accessibility for more details.](/topics/javascript-accessibility/)**

### Landmark roles

Adding ARIA landmark roles to your website is a great way to provide navigational landmarks for people using accessibility tools like screen readers. With roles people using screen readers can jump directly to specific locations on the website.

The major landmark roles for websites are:

- `banner` — for defining an element as the masthead, added to the primary `<header>`.
- `navigation` — for defining an element as the primary navigation, added the the top `<nav>`.
- `search` — for defining an element as being the search field, usually added to a `<form>`.
- `main` — for defining an element as being the main content of the page, same as the `<main>` element, and added to the `<main>`.
- `complementary` — for defining an element as being content related to the primary content, usually added to an `<aside>`.
- `contentinfo` — for defining an element as information about the content: e.g. copyright, terms, privacy policy, usually added to a `<footer>`.

Here’s an example of adding the landmark role to the masthead:

```html
<header role="banner">
  <strong>Accessible Website</strong>
</header>
```

**Links**

- [WAI-ARIA](http://www.w3.org/WAI/intro/aria)
- [Using WAI-ARIA Landmarks](http://www.paciellogroup.com/blog/2013/02/using-wai-aria-landmarks-2013/)

---

## Keyboard focus styles

Not everybody is capable of using a mouse, or even chooses not to use a mouse. But they still need to be able to navigate your website—and keep their position.

Focus styles highlight the currently selected element on screen so it’s recognizable as keyboard focused control.

*It’s important to not remove the keyboard focus rectangle from links, but it can be styled for better contrast or to match your website.*

```css
a:focus {
  outline: 3px solid #000;
}
```

*But don’t ever write `outline: none;` on the `:focus` state—it’s an extremely important feature for keyboard users.*

---

## Skip links

It’s a good idea to add skip links to a website for jumping over the navigation to the main content. Or adding a skip link to jump from the bottom to the top of the website.

Skip links are just standard internal links that jump down to a specific point of a page.

```html
<a href="#main">Jump to main content</a>

⋮

<main role="main" id="main">
```

Most often designers like to hide them but they must be hidden in an accessible manner. Hidden by default but when focused, shown again.

```css
.skip-links a {
  position: absolute;
  top: -3em;
}

.skip-links a:focus {
  top: 0;
}
```

---

## Tools

There are a few things that you should check on every website—at least—to help with accessibility.

*The tools are still no replacement for proper user and accessibility testing.*

1. Bump the font-size up and down to make sure the layout doesn’t break: at least 2 sizes up and 2 sizes down; to make sure you site works with different default styles.
2. Disabled images and see what happens to the layout without them.
3. Disable the CSS to get an idea of what content is available to screen readers.
4. Check the website with [Color Oracle](http://colororacle.org/) to look for colour blindness related issues.
5. Run your website through one or all of the validators.
6. Check all the pages with a screen reader like [VoiceOver](#voiceover).

**[☛ Review the accessibility checklist for more.](/topics/accessibility-checklist/)**

**Tools**

- [Web Developer Toolbar](http://chrispederick.com/work/web-developer/)
- [Color Oracle](http://colororacle.org/)

**Validators**

- [Total Validator](http://www.totalvalidator.com/index.html)
- [Wave by WebAim](http://wave.webaim.org/)
- [Chrome Accessibility Developer Tools](https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb)

---

## Screen readers

Screen readers are accessibility tools to help users with poor vision or complete blindness get the content of a website read out to them.

They parse the content and understand the semantics and read the text out loud. The HTML semantics are interpreted and turned into understandable words.

Many screen readers also present lots of features to help users move around the screen with their keyboard.

Some popular screen readers:

- [NVDA](http://www.nvaccess.org/)
- [Jaws](http://www.freedomscientific.com/Products/Blindness/JAWS)
- [ChromeVox](http://www.chromevox.com/)
- [VoiceOver](https://www.apple.com/accessibility/osx/voiceover/)

### VoiceOver

VoiceOver is the screen reader built into Apple’s operating systems, both desktop and mobile. It doesn’t require any installation, just needs to be turned on.

Here’s some shortcut keys for using VoiceOver:

- `Command + F5` — Turn VoiceOver on/off
- `Control` — Pause VoiceOver
- `Control + Option + Right Arrow` — Move to next item
- `Control + Option + Left Arrow` — Move to previous item
- `Control + Option + U` — Open the rotor
- `Control + Option + Command + H` — Next heading (+ `Shift` for previous)
- `Control + Option + Command + L` — Next link
- `Control + Option + Command + G` — Next graphic
- `Control + Option + Command + X` — Next list

**Links**

- [VoiceOver Commands for Web Page Testing](http://accessibility.psu.edu/voiceover)
- [Using VoiceOver to Evaluate Web Accessibility](http://webaim.org/articles/voiceover/)
- [Apple Accessibility](http://www.apple.com/accessibility/resources/)
- [iOS VoiceOver Gesture, Keyboard & Braille Shortcuts](http://axslab.com/articles/ios-voiceover-gestures-and-keyboard-commands.php)

---

## Video list

1. [Accessibility: ARIA roles](https://www.youtube.com/watch?v=o4xHfi4t9S0&list=PLWjCJDeWfDdcEtSnqq_iGLKGA_H_3o3y7&index=1)
2. [Accessibility: focus styles](https://www.youtube.com/watch?v=js9yaVtV04E&list=PLWjCJDeWfDdcEtSnqq_iGLKGA_H_3o3y7&index=2)
3. [Accessibility: skip links](https://www.youtube.com/watch?v=UnEItq289lU&list=PLWjCJDeWfDdcEtSnqq_iGLKGA_H_3o3y7&index=3)
4. [Accessibility: tools to help find issues](https://www.youtube.com/watch?v=xpqPctbDhnc&list=PLWjCJDeWfDdcEtSnqq_iGLKGA_H_3o3y7&index=4)
5. [Accessibility: validators](https://www.youtube.com/watch?v=FOVKDAt8-oI&list=PLWjCJDeWfDdcEtSnqq_iGLKGA_H_3o3y7&index=5)
6. [Accessibility: VoiceOver](https://www.youtube.com/watch?v=G-EsQ_VHtVM&list=PLWjCJDeWfDdcEtSnqq_iGLKGA_H_3o3y7&index=6)

## Supplemental links

- [Dev.Mozilla: ARIA](https://developer.mozilla.org/en/aria)
- [Simply Accessible](http://simplyaccessible.com/)
- [WebAxe](http://www.webaxe.org/)
- [Paciello Group](http://www.paciellogroup.com/blog/)
- [WebAim](http://webaim.org/)
- [HTML5 Accessibility](http://html5accessibility.com/)
- [456 Berea Street](http://www.456bereastreet.com/)

### Articles

- **[Why Bother with Accessibility](http://24ways.org/2013/why-bother-with-accessibility/)**
- **[WebAim: Web Accessibility for Designers](http://webaim.org/resources/designers/)**
- **[Design and Development: The Yin and Yang of Web Accessibility](http://simplyaccessible.com/article/both/)**
- **[The Sound of the Accessible Title Text Separator](http://www.standards-schmandards.com/2004/title-text-separators/)**
- **[Designing For The Elderly: Ways Older People Use Digital Technology Differently](http://www.smashingmagazine.com/2015/02/05/designing-digital-technology-for-the-elderly/)**
- [The HTML5 Document Outline is a Dangerous Fiction](http://blog.paciellogroup.com/2013/10/html5-document-outline/)
- [Designing For Disabilities: Section 508 and International Accessibility Compliance For Beginners](http://www.sitepoint.com/designing-disabilities-section-508-international-accessibility-compliance-beginners/)
- [Top Mistakes in Web Accessibility](http://www.slideshare.net/wojciechzajac/top-mistakes-in-web-accessibility)
- [Quick Tip Testing Web Content for Screen Readers](http://www.iheni.com/quick-tip-testing-web-content-for-screen-readers-without-a-screen-reader/)
- [User Testing for Web Accessibility](http://sixrevisions.com/usabilityaccessibility/user-testing-web-accessibility/)
- [Web writer’s accessibility checklist](http://www.4syllables.com.au/resources/templates-checklists/accessibility-checklist/)
- [WCAG: Quick Reference](http://www.w3.org/WAI/WCAG20/quickref/)
- [Extending Semantics & Accessibility](http://learn.shayhowe.com/advanced-html-css/semantics-accessibility)
- [WebVTT and Video Subtitles](http://www.iandevlin.com/blog/2011/05/html5/webvtt-and-video-subtitles)

### Videos

- **[How A Blind Person Uses A Computer](https://www.youtube.com/watch?v=UzffnbBex6c)**
- **[How Blind People Use Twitter & You Tube on the iPhone 4S](https://www.youtube.com/watch?v=c0nvdiRdehw)**
- [iPhone, iPad and Apple VoiceOver](https://www.youtube.com/watch?v=QEDzitE2w_0)
- [Christopher Hills: One Switch. One Head. The World.](https://www.youtube.com/watch?v=cSSgndQ5mVs)
- [No Hands Ken](https://www.youtube.com/watch?v=XrMivdZ-mbI)
- [WebAxe: Accessibility Videos](http://www.webaxe.org/accessibility-videos/)
- [Videos of Screen Readers Using ARIA](http://zomigi.com/blog/videos-of-screen-readers-using-aria/)

### Books

- [WebAxe: Free Online Books on Accessibility](http://www.webaxe.org/free-online-books-on-accessibility/)
- [Paciello Group: Books](http://www.paciellogroup.com/resources/books)
- [InterACT with Web Standards](http://www.amazon.ca/dp/0321703529/), Chapters 22–24

### Tools

- **[Color Contrast Analyser](http://www.paciellogroup.com/resources/contrastAnalyser)**
- [AccessLint](http://www.accesslint.com/)
- [HTML5 Outliner](http://gsnedders.html5.org/outliner/)
- [HTML5 Outliner Chrome Extension](https://chrome.google.com/webstore/detail/afoibpobokebhgfnknfndkgemglggomo)
- [Lynx Viewer](http://www.clickability.co.uk/lynx-viewer.php)

### Standards

- [WCAG 2.0](http://www.w3.org/TR/WCAG20/)
- [WAI-ARIA](http://www.w3.org/TR/wai-aria/)

### Checklists

- [WebAim: Checklist](http://webaim.org/standards/wcag/checklist)
- [W3: Checklist](http://www.w3.org/TR/2006/WD-WCAG20-20060427/appendixB.html)

### People

- [Steve Faulkner](http://www.paciellogroup.com/) [@stevefaulkner](http://twitter.com/stevefaulkner)
- [John Foliot](http://john.foliot.ca/) [@johnfoliot](http://twitter.com/johnfoliot)
- [Roger Johansson](http://www.456bereastreet.com/) [@rogerjohansson](http://twitter.com/rogerjohansson)
- Steve Buell [@SteveBuell](http://twitter.com/SteveBuell)
- [Everett Zufelt](http://zufelt.ca/) [@ezufelt](http://twitter.com/ezufelt)
