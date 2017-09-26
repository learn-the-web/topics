---
title: "CSS animations & effects cheat sheet"
tags: "css effects transitions animations transforms cheat sheet"
desc: "A cheat sheet describing the different code involved in making CSS transitions & animations."
layout: cheatsheet

groups:
  - title: "Transforms"
    items:
      - name: '`transform: rotate(deg)`'
        details:
          - 'Rotate an element and any children a certain number of degrees.'
          - 'Can use negative numbers to go backwards.'
          - |
            ```css
            .dino {
              transform: rotate(-33deg);
            }
            ```
      - name: '`transform: translate(x, y)`'
        details:
          - 'Similar to `position relative`; will move an element around on the screen without affecting other elements.'
          - 'The position is based on where the element is currently located.'
          - |
            ```css
            .dino {
              /* Move rightwards 5em and no vertical movement */
              transform: translate(5em, 0);
            }
            ```
          - 'Has companion functions to move only in one direction:'
          - |
            ```css
            transform: translateX();
            transform: translateY();
            ```
      - name: '`transform: scale(factor)`'
        details:
          - 'Grow or shrink an element and all its children.'
          - '`1` is what the element currently is; `.6` is smaller; `2.3` is bigger.'
          - |
            ```css
            .dino {
              transform: scale(1.4);
            }
            ```
          - 'Has companion functions to scale only in one direction:'
          - |
            ```css
            transform: scaleX();
            transform: scaleY();

            /* Or combined together */
            transform: scale(1.4, 3);
            ```
      - name: '`transform: skew(deg, deg)`'
        details:
          - 'Skew an element horizontally and vertically.'
          - |
            ```css
            .dino {
              /* Leaving the second value off will only skew horizontally */
              transform: skew(12deg);
            }
            ```
          - 'Has companion functions to skew only in one direction:'
          - |
            ```css
            transform: skewX();
            transform: skewY();
            ```
      - name: '**Multiple transforms**'
        details:
          - 'Written on a single line, separated by a space.'
          - |
            ```css
            .dino {
              transform: rotate(33deg) scale(1.4);
            }
            ```
      - name: '*Multiple transforms—incorrect example*'
        details:
          - 'Multiple lines won’t work.'
          - 'Only the second entry will be activated.'
          - |
            ```css
            .dino {
              /* WRONG */
              transform: rotate(33deg);
              transform: scale(1.4);
            }
            ```

  - title: "Transitions"
    note: "Requires user interaction to trigger."
    items:
      - name: '`transition: all 1s linear`'
        details:
          - 'Transition `all` numerical properties that changed.'
          - 'Lasting `1s`'
          - 'With `linear` easing (no easing).'
          - |
            ```css
            .dino {
              transition: all 1s linear;
            }
            ```
      - name: '`transition: background-color 1s linear`'
        details:
          - 'Transition only the `background-color`.'
          - |
            ```css
            .dino {
              transition: background-color 1s linear;
            }
            ```
      - name: '`transition: all 1s 2s linear`'
        details:
          - 'Delay starting the transition for `2s`'
          - |
            ```css
            .dino {
              transition: all 1s 2s linear;
            }
            ```
      - name: '**Multiple transitions**'
        details:
          - 'Written on a single line, separated by a comma.'
          - |
            ```css
            .dino {
              transition: background-color 1s linear, color .5s linear;
            }
            ```
      - name: '*Easings*'
        details:
          - '`linear`, `ease`, `ease-in`, `ease-out`, `ease-in-out`'
          - '`steps()` — instead of a smooth transition, specific number of frames.'
          - |
            ```css
            .dino {
              transition: background-position 1s steps(4);
            }
            ```
          - 'Create your own with `cubic-bezier()`—[Cubic Bezier Generator](http://cubic-bezier.com/)'
      - name: '**Always on the original state**'
        details:
          - 'Do not put `transition` in `:hover`—it won’t do what you expect.'
          - |
            ```css
            .dino:hover {
              /* WRONG */
              transition: all 1s linear;
            }
            ```

  - title: "Animations"
    note: "Can play automatically or on user interaction."
    items:
      - name: '`@keyframes`'
        details:
          - 'First component of an animation.'
          - 'Name the keyframes whatever you’d like—following [naming conventions](/topics/naming-paths-cheat-sheet/).'
          - |
            ```css
            @keyframes wiggle {}
            @keyframes dance {}
            @keyframes faderoo {}
            @keyframes blabidy-boo {}
            ```
      - name: '`@keyframes` keywords'
        details:
          - 'Use the start & end keywords.'
          - |
            ```css
            @keyframes wiggle {

              start {
                transform: translateX(-2em);
              }

              end {
                transform: translateX(-4em);
              }

            }
            ```
      - name: '`@keyframes` percentages'
        details:
          - 'Use percentages to define the different animation keyframes.'
          - |
            ```css
            @keyframes wiggle {

              0% {
                transform: translateX(0em);
              }

              40% {
                transform: translateX(-2em);
              }

              80% {
                transform: translateX(2em);
              }

              100% {
                transform: translateX(0em);
              }

            }
            ```
      - name: '`animation: wiggle 1s linear`'
        details:
          - 'Use the keyframes set named `wiggle`'
          - 'Make the animation last `1s`'
          - 'Have `linear` (no) easing.'
          - |
            ```css
            .dino {
              animation: wiggle 1s linear;
            }
            ```
      - name: '`animation: wiggle 1s 2s linear`'
        details:
          - 'Delay starting the animation for `2s`'
          - |
            ```css
            .dino {
              animation: wiggle 1s 2s linear;
            }
            ```
      - name: '`animation: wiggle 1s linear infinite`'
        details:
          - '`infinite` — Animation iteration count: loop the animation keyframes infinite number of times.'
          - 'Use a number to choose how many interations.'
          - |
            ```css
            .dino {
              animation: wiggle 1s linear infinite;
            }

            .moon {
              /* Play the animation 5 times */
              animation: wiggle 1s linear 5;
            }
            ```
      - name: '`animation: wiggle 1s linear alternate`'
        details:
          - '`alternate` — Animation direction: play the keyframes forwards then backwards.'
          - 'Directions: `normal`, `reverse`, `alternate`, `alternate-reverse`'
          - |
            ```css
            .dino {
              animation: wiggle 1s linear alternate;
            }
            ```
      - name: '`animation: wiggle 1s linear forwards`'
        details:
          - '`forwards` — Animation fill mode: keep the animation on its last frame when complete.'
          - 'Modes: `forwards`, `backwards`'
          - |
            ```css
            .dino {
              animation: wiggle 1s linear forwards;
            }
            ```
      - name: '*Easings*'
        details:
          - '`linear`, `ease`, `ease-in`, `ease-out`, `ease-in-out`'
          - '`steps()` — instead of a smooth transition, specific number of frames'
          - |
            ```css
            .dino {
              animation: wiggle 1s steps(4);
            }
            ```
          - 'Create your own with `cubic-bezier()`—[Cubic Bezier Generator](http://cubic-bezier.com/)'
      - name: '*Combine multiple options together*'
        details:
          - |
            ```css
            .dino {
              animation: dance 1s 2s 6 alternate;
            }
            ```
          - 'Use the `dance` keyframes, play the animation for `1s`, wait `2s` to start the animation, loop the keyframes `6` times, and `alternate` the keyframe play direction forwards & backwards'
      - name: '`animation` on `:hover`'
        details:
          - 'Put `animation` in `:hover` to trigger when interacted with'
          - |
            ```css
            .dino:hover {
              animation: dance .3s linear;
            }
            ```

  # - title: 'Filters'
  #   notes: 'Be careful with image filters, they’re very memory intensive and can slow your website down significantly. [See more filters](https://developer.mozilla.org/en-US/docs/Web/CSS/filter).'
  #   items:
  #     - name: '`grayscale()`'
  #     - name: '`blur()`'
  #     - name: '`brightness()`'
  #     - name: '`contrast()`'
  #     - name: '`saturate()`'
  #     - name: '`sepia()`'
  #     - name: '`drop-shadow()`'
  #     - name: '*Multiple filters*'
  #     - name: '*Filters & hover*'

  - title: "Target"
    items:
      - name: '`:target`'
        details:
          - 'Style an element when the URL matches the `id` of an element.'
          - 'URL: `https://dinos-r-us.ca/#stego`'
          - |
            ```html
            <h1 id="stego">Stegosaurus</h1>
            ```
          - |
            ```css
            #stego {
              background-color: yellow;
            }

            #stego:target {
              background-color: yellow;
            }
            ```
      - name: '*Target links*'
        details:
          - |
            ```html
            <ul>
              <li><a href="#stego">Stegosaurus</a></li>
              <li><a href="#tri">Triceratops</a></li>
            </ul>

            <div class="dino" id="stego">…</div>
            <div class="dino" id="tri">…</div>
            ```
          - |
            ```css
            .dino {
              border: 1px solid #e2e2e2;
            }

            .dino:target {
              border-color: #f33;
            }
            ```
      - name: '*Animate when targeted*'
        details:
          - |
            ```html
            <a href="#dino">Go Dino, Go!</a>

            <img id="dino" src="images/dino.svg" alt="Big Dinosaur">
            ```
          - |
            ```css
            #dino:target {
              animation: wiggle 1s linear;
            }
            ```
---
