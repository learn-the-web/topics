---
layout: cheatsheet
group: web-dev-3

groups:
  - title: 'Syntax'
    items:
      - name: '*Operators*'
        details:
          - '`+` — addition with numbers, concatenation with strings.'
          - '`-` — subtraction.'
          - '`*` — multiplication.'
          - '`/` — division.'
          - '`%` — modulus: get the remainder.'
          - '`++` — add 1 onto the number.'
          - '`--` — subtract 1 from the number.'
          - '`+=` — add to the number.'
          - '`-=` — subtract from the number.'
          - '`-=` — multiply the number.'
          - '`-=` — divide the number.'
      - name: '*Logic*'
        details:
          - '`==` — check if values are the same.'
          - '`===` — check if values are the same, strictly—must be same data type.'
          - '`!=` — check if values are different.'
          - '`!==` — check if values are different, strictly—type is also checked.'
          - '`<=` — less than or equal to.'
          - '`>=` — greater than or equal to.'
          - '`>` — greater than.'
          - '`<` — less than.'
          - '`&&` — and.'
          - '`||` — or.'
      - name: '*Math*'
        details:
          - '`Math.random()` — generate a random number between 0 and 1.'
          - '`Math.round()` — round the number to an integer.'
          - '`Math.ceil()` — round the number up.'
          - '`Math.floor()` — round the number down.'
      - name: '*Variables*'
        details:
          - |
            ```js
            var name = 'Triceratops'; // String
            var numberHorns = 3; // Number
            var isHerbivore = true; // Boolean
            // Array
            var carnivores = ['Tyrannosaurus', 'Velociraptor'];
            // Object
            var spino = {
              name: 'Spinosaurus',
              isHerbivore: false
            }
            ```
      - name: '*Strings*'
        details:
          - '`+` — combine (concatenate) strings together.'
          - '`length` — count how many characters are in the string.'
          - '`toUpperCase()` — convert all the letters to upper case.'
          - '`toLowerCase()` — convert all the letters to lower case.'
          - '`slice(from, to)` — get a chunk of text up to a specific point.'
          - '`substr(from, length)` — get a chunk from the text of a specific length.'
          - "`replace('…', '…')` — change one or more instances to something else."
          - "`split('…')` — create an array by breaking the string on a specific character."
          - '`trim()` — remove spaces at the start and end.'
      - name: '*Arrays*'
        details:
          - '`things[1]` — get a specific item from the array.'
          - '`length` — count how many items are in the array.'
          - '`push(…)` — add to the end of the array.'
          - '`pop()` — remove from the end of the array.'
          - '`unshift(…)` — add to the start of the array.'
          - '`shift()` — remove from the start of the array.'
          - '`delete things[1]` — delete an item from the array.'
      - name: '*If-statements*'
        details:
          - |
            ```js
            if (planet == 'Venus') {
              // True path
            } else {
              // False path
            }
            ```
      - name: '*Loops*'
        details:
          - |
            ```js
            var planets = ['Mercury', 'Venus', 'Earth', 'Mars'];
            var i = 0;
            var totalPlanets = planets.length;

            for (i = 0; i < totalPlanets; i++) {
              // For-loop
            }

            planets.forEach(function (item)) {
              // For-each loop
            });
            ```
      - name: '*Switches*'
        details:
          - |
            ```js
            var planet = 'Venus';

            switch (planet) {
              case 'Mercury' :
                break;

              case 'Venus' :
                break;

              case 'Mars' :
                break;
            }
            ```


  - title: 'JS + HTML'
    items:
      - name: '*Objects*'
        details:
          - ''
          - ''
      - name: '*Objects*'
        details:
          - ''
          - ''


---
