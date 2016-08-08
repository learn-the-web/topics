---
playlist: PLWjCJDeWfDdcKlUX7kWCdphdZkSOOlOFU
download: https://github.com/acgd-learn-the-web/javascript-intro-code/archive/master.zip
github: https://github.com/acgd-learn-the-web/javascript-intro-code
cheatsheet: javascript-cheat-sheet
checklist: javascript-checklist
---

Javascript is a general purpose programming language originally created for use inside web browsers, but now works just as well on servers.

The syntax is very similar to other popular languages including [PHP](http://en.wikipedia.org/wiki/PHP), [Perl](http://en.wikipedia.org/wiki/Perl) and [Java](http://en.wikipedia.org/wiki/Java_(programming_language))—they all sharing similar structure of parenthesis, brackets, and semi-colons.

---

## Creating & attaching a Javascript file

A Javascript file is no different than any other web code files—just a plain old text file.

Usually they’re stored inside a “js” folder in your website.

When connecting the Javascript, it’s almost always a good idea to add the Javascript to the bottom of your HTML file—immediately above the closing `</body>` tag.

Using the `script` tag we can point to our Javascript file.

```html

  <script src="js/main.js"></script>
</body>
</html>
```

We always put our JS files at the bottom of our HTML for 2 reasons:

1. **Performance** — JS is a blocking resource, which means it forces the browser to wait for it to finish downloading before the browser can continue rendering.
  Our users perceive that the website loads faster if it gets rendered before the JS starts downloading
2. **HTML manipulation** — we want to manipulate HTML with our JS, but the HTML must be rendered to the screen before JS can do anything

---

## Program flow

When our Javascript is executed by the browser it starts at the top and works it’s way down the code file.

The order of operations can be controlled and reordered using different programming paradigms like if-statements, loops, events, and more.

---

## Naming things

In Javascript, when naming variables, functions, etc. there’s a common convention we follow, called “Camel Case”.

With camel case, we mash words together without separators, but use capitalization to distinguish the words.

1. The first letter is lowercase
2. Every word after that is capitalized

Some examples:

- `solarSystem` — starts with a lowercase, then each word has capital
- `thisVariableIsReallyLong` — each new word has a capital letter
- `isHuman` — with booleans, often the word `is` is used at the start
- `ImportantThing` — when the first letter is capitalized, it’s called “Upper Camel Case”

---

## Comments

Comments are great for helping write documentation or even debugging—Javascript has two flavours of comments.

```js
// Single line comments

/*
  Multi-line
  comments
*/
```

---

## Variables

Javascript is a dynamic language, you don’t have to declare what data type your variable will hold before assigning it a value. Use the var keyword to define and create a new variable.

Variables are just named containers that hold some data for us. We can retrieve that data later using the variable’s name.

```js
// Create a new variable and set its value
var closestStar = 'Proxima Centauri';
```

- Variable names must start with a letter (a–z or A–Z), underscore (_), or dollar sign ($) and should only contain letters, numbers (0–9), underscores, and dollar signs.
- Variable names *are* case-sensitive.
- The naming convention in Javascript is to use camel case to distinguish words.

```js
// Multiple variables can be declared with one var keyword
// Use a comma (,) to separate the declarations
var closestStar = 'Sun',
  nextClosestStar = 'Proxmia Centauri'
;
```

**Links**

- [MDN: Variables and values](https://developer.mozilla.org/en/JavaScript/Guide/Values%2c_Variables%2c_and_Literals)

---

## Data types

There are some basic data types in Javascript that you should be familiar with.

### Strings

Strings in Javascript, are really just plain old text. All strings in Javascript must be surrounded by quotes—either single or double, Javascript doesn’t care.

```js
// Strings: basic text and words
// Single (') or double quotes (") can be used
var galaxy = 'Milky Way',
  closestGalaxy = "Canis Major Dwarf"
;
```

### Numbers

In Javascript, numbers are not in quotes, that’s the distinction between plain text and numbers. Numbers allow mathematical operations on them, whereas strings to not.

```js
// Numbers: integer or float (decimal)
var totalPlanets = 8,
  moonTemperature = -153,
  axialTilt = 23.4,
  lightSpeed = 3e8
;

// This isn't a number because it’s inside quotes
var notANumber = '58';
```

### Boolean

Boolean values are just `true` or `false`—that’s all.

```js
// Booleans: true/false (yes/no)
var hasWater = true,
  isHabitable = false
;
```

**Links**

- [MDN: data structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)

---

## Operators

The operators in Javascript are fairly consistent with many other languages.

```js
// Addition: with +
var add = 1 + 2,
  number += 2 // Add to what’s already in number
;
number++; // Increment: add 1 to what’s already in number

// Subtraction: with -
var minus = 2 - 1;
number -= 2; // Minus from what’s already in number
number--; // Decrement: subtract 1 from what’s already in number

// Multiplication: with *
var times = 1 * 2;
number *= 2; // Multiply what’s already in number

// Division: with /
var divide = 4 / 2;
number /= 2; // Divide what’s already in number

// Modulus: with %
var remainder = 4 % 2; // Return the remainder after division
number %= 2; // Get remainder with what’s already in number
```

### String joining

Javascript, as with many modern programming languages, allows you to join together multiple strings and variables. To combine strings and variables in Javascript use the plus (+).

```js
// Use the plus (+) to join strings and variables
var galaxy = 'Milky Way',
  ourGalaxy = galaxy + ' is our galaxy.' // Milky Way is our galaxy.
;

// Join two variables together
var words = ' is our galaxy.';
ourGalaxy = galaxy + words; // Milky Way is our galaxy.

// Use += to add onto a string
galaxy += words; // Milky Way is our galaxy.
```

*The plus is called a string concatenator.*

**Links**

- [MDN: Operators](https://developer.mozilla.org/en/JavaScript/Guide/Expressions_and_Operators)

---

## Functions

Functions in Javascript are a group of reusable code in your program. They are stored inside variables like every other types of data.

```js
// This function will write out a dinosaur name
// After creating the name of your variable, you set it to be a function
var writeDinoName = function () {
  document.write('Apatosaurus');
};
```

After the function has been created, you can call it multiple times:

```js
writeDinoName();
writeDinoName();
writeDinoName();
```

This will execute the function three times. We know the function is being executed because it’s the variable name immediately followed by brackets.

### Arguments

The function above isn’t terribly reusable because it will always output the same thing. Using arguments, or function-scoped variables, we can make the function do different things.

When defining a function, create a new argument, practically the same thing as a variable, between the function definition’s brackets.

```js
// The `name` is the argument, allowing information to be sent into the function
var writeADino = function (name) {
  // We can then use `name` any way we'd normally use a variable
  document.write(name);
};

// We can then send information into the function and it will use that while executing
writeADino('Iguanodon');
writeADino('Stegosaurus');
```

Functions can actually have multiple arguments.

```js
// Two arguments: `name` and `diet`, just add another after a comma
var writeADinoDiet = function (name, diet) {
  document.write(name + ' is a ' + diet);
};

// Send both pieces of information into our function
writeADinoDiet('Triceratops', 'Herbivore');
// This would output: Velociraptor is a Carnivore
writeADinoDiet('Velociraptor', 'Carnivore');
```

**Links**

- [MDN: function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)

---

## Arrays

Arrays contain a collection of items in a specific order. Each item in an array is referenced using an integer. If you’re familiar with HTML you could compare arrays to ordered lists `<ol>`.

```js
// New empty array
var planets = [];
// An array with elements inside
planets = ['Jupiter', 'Saturn', 'Neptune'];

// Items in an array are referenced by their key
// The key will be an integer, starting at 0
// Get the first item from the array
planets[0]; // Jupiter
// Get the third item from the array (the numbers start at 0)
planets[2]; // Neptune

// Replace the item at key 3
planets[3] = 'Venus';
// Add a new item to the end of an array
planets.push('Mercury');

// Remove the last item from our array
var lastLast = planets.pop();
// Add a new item to the start of an array
planets.unshift('The Sun');
// Remove an item from the start of an array
var firstPlanet = planets.shift();

// Delete an item from an array
delete planets[2];

// Count how many items are in the array
planets.length; // 4
```

*Check out [For-each loops](#for-each-loops) to see how to loop over an array.*

**Links**

- [MDN: array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

---

## Objects

Objects are a way to create a group of variables. Objects are a collection with properties and values. If you’re familiar with HTML, objects are comparable to the description list `<dl> <dt> <dd>`.

```js
// Create a new empty object
var planetEarth = {};

// Create properties inside of an object
// Properties can be anything we want
// Separate each property with a comma (,)
planetEarth = {
  population: 6.5e9,
  numberMoons: 1,
  starSystem: 'Solar'
};

// Get the property from the object with the name ‘population’
planetEarth.population; // 6.5e9
// Add/replace the property with the name ‘diameter’
planetEarth.diameter = 12756;
// Remove a property from an object
delete planetEarch.numberMoons;

// Objects can even have arrays inside them
// And other objects!
var solarSystem = {
  innerPlanets: ['Mercury', 'Venus', 'Earth', 'Mars'],
  sunFacts: { diameter: 1392000, mass: 2e30 }
};

// There is an alternative syntax for accessing properties
//   it can be used when the property contains invalid characters
planetEarth['semi-major axis'];
// Or when the property name is stored in a variable
var propName = 'starSystem';
planetEarth[propName]; // Solar
```

**Links**

- [MDN: Objects](https://developer.mozilla.org/en/JavaScript/Guide/Working_with_Objects)

---

## If-statements

If-statements add logic-based control to our code; they allow us to perform one action or another action.

```js
var planet = 'Venus';

// Compare the variable planet to the string ‘Venus’
if (planet == 'Venus') {
  // If planet is equal to ‘Venus’ then execute this code
}
```

- The double equals (==) means compare. It’s best to not use a single equals in an if-statement. [Read more about equals](#single-equals-vs-double-equals-vs-triple-equalsequals).
- If-statements are always looking for a truthy scenario. The if-statement is looking to see if the comparison between the opening and closing parenthesis is true. If the comparison is truthy the if-statement is executed.

```js
var planet = 'Earth',
  hasMoon = true
;

// Since the variable is true, we don’t have to compare against true
// The if-statement is always checking for a truthy scenario
if (hasMoon) {
  // Execute this code if the scenario is truthy
} else {
  // Execute this code if the scenario is falsey
  // The else leaves us a catch all if the first scenario is falsey
}
```

### And/or

Often it’s helpful to compare multiple situations at once in our if-statements. To do this we use ‘or’ and ‘and’ clauses.

```js
var planet = 'Venus',
  isSecond = true,
  hasMoons = false
;

// And: one situation AND the other must be truthy
// And is represented by two ampersands (&&)
if (planet == 'Venus' && isSecond) {
  // This will execute because planet is equal to ‘Venus’ and isSecond is also truthy
}

if (planet == 'Venus' && hasMoons) {
  // This will not execute because only the first scenario is truthy
}

// Or: one situation OR the other must be truthy
// Or is represented by two vertical pipes (||)
if (planet == 'Venus' || isSecond) {
  // This will execute because both situations are truthy
}

if (planet == 'Mercury' || planet == 'Venus') {
  // This will execute because one of the two situations is truthy
}

if (hasMoons || isSecond) {
  // This will execute because one of the two situations is truthy
}

if (hasMoons || planet == 'Mercury') {
  // This will not execute because neither situation is truthy
}
```

### Not equal

We can also compare to see if two things are not equal.

```js
var planet = 'Venus',
  isSecond = true,
  hasMoons = false
;

// Not equals is represented by an exclamation point and equals (!=)
if (planet != 'Mercury') {
  // This will execute because it is true that planet is not equal to ‘Mercury’
}

if (planet != 'Venus') {
  // This will not execute because planet is equal to ‘Venus’
}

// Not is represented by an exclamation point (!)
// The below could be read as ‘has moons is not equal to true’ or ‘not has moons’
if (!hasMoons) {
  // This will execute because this scenario is truthy, hasMoons is not equal to true
}

if (!isSecond) {
  // This will not execute because isSecond is true, not false
}

if (!hasMoons && planet == 'Venus') {
  // This will execute because both scenarios are truthy
}
```

### Single equals vs. double equals vs. triple equals

Equals can be used in a series of up to three in Javascript, each meaning slightly different things and acting differently.

*1. single equals means ‘set’*

```js
var planet = 'Mars';
```

*2. double equals means ‘compare’*

```js
if (planet == 'Mars') {}
```

*3. triple equals means ‘compare exactly’*

```js
// Will compare the value of planet to see if it equals ‘Mars’ and that the value is a string
if (planet === 'Mars') {
  // This will be executed because planet is a string and it’s equal to ‘Mars’
}

// Will compare to see if the value of planet is truthy
if (planet == true) {
  // This will execute because the value of planet is truthy
  // Check out type coercion for more details
}

// Will compare the value of planet to see if it’s true and to see if it is a boolean
if (planet === true) {
  // This will not execute because planet is not exactly ‘true’
}
```

### Type coercion

Type coercion occurs inside the if-statement when trying to get a truthy value. Since Javascript is a dynamically interpreted language certain, values are coerced to boolean, becoming true or false.

Value | Coerced boolean
--- | ---
`0` | `false`
`0.0` | `false`
`''` | `false`
`'0'` | `false`
`[]` | `false`
`null` | `false`
`undefined` | `false`
`1` | `true`
`-1` | `true`
`3e8` | `true`
`'Mars'` | `true`
`'false'` | `true`
`[1]` | `true`

*If it’s not in the list, chances are it will be coerced to true.*

```js
var planet = 'Mars';

if ('Mars') {} // True

if (planet) {} // True

if (0.0) {} // False
```

**Links**

- [MDN: If](https://developer.mozilla.org/en/JavaScript/Reference/Statements/if...else)

---

## Loops

Programming languages provide mechanisms for repeating a section of code: loops. There are a bunch of different loop types in Javascript—the for loop is popular.

### For loop

For loops are fast and great if we know exactly how many items we have to loop through.

```js
// The `i` variable is a counter, to count how many times the loop has occurred
var i;

// Let’s create a loop that repeats 5 times
for (i = 0; i < 5; i++) {
  // The code in here will be executed 5 times
}

// Inside the loop declaration we define how the loop performs
// There should be three expressions, each separated by a semi-colon
//   for (expression 1; expression 2; expression 3)

// Expression 1: executed once before the loop starts
for (i = 0; …; …) {}
// We are creating a variable named i, that tracks what iteration we are currently on

// Expression 2: executed at each iteration,
//   if true the loop continues
for (…; i < 5; …) {}
// We are checking to see if i is less than 5, if so, we continue the loop

// Expression 3: executed after each iteration
for (…; …; i++) {}
// Increment i by 1 each pass through the loop
```

This loop will write out the word “Hello.” 10 times.

```js
var i;

for (i = 0; i < 10; i++) {
  document.write('Hello.');
}
```

### While loop

While loops are for when you don’t know exactly how many times you have to loop. They have a syntax similar to if-statements where you use logic to determine if the loop should continue.

```js
var favPlanet;

// This loop will keep prompting the user until they type something into the prompt field
// As long as favPlanet coerces to a falsey value the loop will continue
while (!favPlanet) {
  favPlanet = prompt("What's your favourite planet?");
}
```

### For-each loop

For-each loops are used for looping over arrays:

```js
var planets = ['Mercury', 'Venus', 'Earth', 'Mars'];

planets.forEach(function (item)) {
  // The code in here will be executed once for each array item
  // `item` will be filled with the content of each item in the array
  document.write(item);
});
```

**Links**

- [MDN: for](https://developer.mozilla.org/en/JavaScript/Reference/Statements/for)
- [MDN: while](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while)
- [MDN: forEach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)

---

## Switches

Javascript has another control structure that has a similar purpose to the if-statement but allows multiple scenarios.

```js
var planet = 'Venus';

// The switch statement is used when there are many different paths for your code
switch (planet) {
  case 'Mercury' :
    // If planet is ‘Mercury’ this code will be executed
    break;

  case 'Venus' :
    // If planet is ‘Venus’ this code will be executed
    break;

  case 'Mars' :
    // If planet is ‘Mars’ this code will be executed
    break;
}
```

The switch statement also has an ‘else’ like mechanism: `default`.

```js
var planet = 'Venus';

switch (planet) {
  case 'Mercury':
    // If planet is ‘Mercury’ this code will be executed
    break;

  case 'Venus':
    // If planet is ‘Venus’ this code will be executed
    break;

  default:
    // If none of the above conditions are met this code will be executed
    // Default must always be last, like else
    break;
}

// We can also group pieces of code together for when multiple situations are satisfied by the same code, like an ‘or’
// The break keyword stops the case from grouping with the one below
switch (planet) {
  case 'Mercury' :
    // If planet is ‘Mercury’ this code will be executed
    break;

  case 'Venus':
  case 'Mars':
    // If planet is ‘Venus’ or ‘Mars’ this code will be executed
    break;

  case 'Earth':
  default:
    // If planet is ‘Earth’ or anything else
    break;
}
```

**Links**

- [MDN: switch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch)

---

## Manipulating strings

Manipulating strings in programming is a very common task. Javascript has a bunch of functions to help you manipulate text.

```js
var name = 'Iguanodon bernissartensis';

// Convert the text to all upper case letters
name.toUpperCase();
// Convert the text to all lower case letters
name.toLowerCase();

// Extract characters 7 - 11
name.slice(7, 11);
// Extract characters starting a 7, going 4 characters long
name.substr(7, 4);

// Count how many characters are in a string
name.length;

// Replace the `a` with an `@`
name.replace('a', '@');

// Break the text apart on the space
var nameBits = name.split(' ');
// It becomes an array, and you can pick apart each part of the array
console.log(nameBits);
console.log(nameBits.length);
console.log(nameBits[1]);

// Remove extra space from the start and end of the string
var dino = '   Iguanodon   ';
dino.trim(); // 'Iguanodon'
```

---

## Semicolons

In Javascript, not all instructions require a semicolon (;) at the end of the statement. The Javascript language uses Automatic Semicolon Insertion, but it can be tricky.

- [Are semi-colons necessary in Javascript?](http://aresemicolonsnecessaryinjavascript.com/)
- [Semicolons in Javascript are Optional](http://mislav.uniqpath.com/2010/05/semicolons/)
- [Javascript semicolon insertion: everything you need to know](http://inimino.org/~inimino/blog/javascript_semicolons)

---

## Video list

1. [Javascript: introduction](https://www.youtube.com/watch?v=j2ppuBwAATg&index=1&list=PLWjCJDeWfDdcKlUX7kWCdphdZkSOOlOFU)
2. [Javascript: program flow](https://www.youtube.com/watch?v=WxRwf5KvNVI&index=2&list=PLWjCJDeWfDdcKlUX7kWCdphdZkSOOlOFU)
3. [Javascript: variables & strings](https://www.youtube.com/watch?v=czTWbdwbt7E&index=3&list=PLWjCJDeWfDdcKlUX7kWCdphdZkSOOlOFU)
4. [Javascript: numbers](https://www.youtube.com/watch?v=LLAd7PybpdQ&index=4&list=PLWjCJDeWfDdcKlUX7kWCdphdZkSOOlOFU)
5. [Javascript: boolean datatypes](https://www.youtube.com/watch?v=tScxERK1fMY&index=5&list=PLWjCJDeWfDdcKlUX7kWCdphdZkSOOlOFU)
6. [Javascript: if-statements & boolean logic](https://www.youtube.com/watch?v=4lATbwt87Cs&index=6&list=PLWjCJDeWfDdcKlUX7kWCdphdZkSOOlOFU)
7. [Javascript: loops](https://www.youtube.com/watch?v=ClT5XRDOEIY&index=7&list=PLWjCJDeWfDdcKlUX7kWCdphdZkSOOlOFU)
8. [Javascript: functions](https://www.youtube.com/watch?v=-o4NCu7v4Ug&index=8&list=PLWjCJDeWfDdcKlUX7kWCdphdZkSOOlOFU)
9. [Javascript: arrays](https://www.youtube.com/watch?v=ENU7mdIlCFA&index=9&list=PLWjCJDeWfDdcKlUX7kWCdphdZkSOOlOFU)
10. [Javascript: objects](https://www.youtube.com/watch?v=3otasvikEls&index=10&list=PLWjCJDeWfDdcKlUX7kWCdphdZkSOOlOFU)
11. [Javascript: string manipulation](https://www.youtube.com/watch?v=XGo2qjc9acU&index=11&list=PLWjCJDeWfDdcKlUX7kWCdphdZkSOOlOFU)

## Supplemental links

- **[MDN: Language reference](https://developer.mozilla.org/en/JavaScript)**
- **[Eloquent Javascript](http://www.amazon.ca/dp/1593272820/)**
- **[Javascript resources](https://www.javascript.com/resources)**
- [A re-introduction to JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript)
- [Javascript Garden](https://bonsaiden.github.io/JavaScript-Garden/)
- [JavaScript and JQuery: Interactive Front-End Web Development](http://www.amazon.ca/dp/1118531647)
- [ThinkVitamin: Javascript](http://membership.thinkvitamin.com/library/javascript)
- [Javascript: The Good Parts](http://www.amazon.ca/dp/0596517742/)
- [Codecademy](http://www.codecademy.com/)
- [WikiBooks: Javascript](http://en.wikibooks.org/wiki/JavaScript/Control_Structures)
- [Learn JavaScript and Up Your Photoshop Game](http://blog.teamtreehouse.com/learn-javascript-photoshop-game)
- [Javascript in one pic](https://github.com/coodict/javascript-in-one-pic)
