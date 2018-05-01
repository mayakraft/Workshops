# Introduction to Coding: Javascript, Data, and Poetry

### May 7, The Metropolitan Library Council of New York

## Program Outline

1. "What is code?" (15 min)
2. HTML and CSS (30 min)
3. Javascript: Memory & Loops (2 hr)
   * Storage
   * Arithmetic
   * Control Flow
4. Javascript: Functions (1 hr)
   * Event Handlers
   * Callbacks
5. Data: JSON (45 min)
   * Fetch from the internet
6. Generative Systems (45 min)

### Summary of in-class exercises

* Hyperlink between 2 HTML pages
* Dice roll
* Random friend picker
* Generative color swatch
* One million dollars
* Drawing with the mouse
* Create a JSON
* Classmates on Google Maps
* Markov-chain poetry

### Student prep

1. Download [Sublime Text](http://www.sublimetext.com) and [Chrome Browser](http://www.google.com/chrome/)
2. Create one folder (anywhere on your computer), this will house all our files.

### Teacher prep

1. Create a shared doc (Google Docs, Dropbox Paper) and share the link with the class.


---

# Sessions

## 1. Introduction: what is code?

> ### DURATION: 15 MINUTES

### Old Technology

#### Imagine

You and your friend are copying a document on a printing press. Your friend is assembling the punches, and your job is to dictate the text and layout. How do you say to your friend "now switch to bold" instead of it sounding like the words "now switch to bold" are inside the text?

* say it louder (change volume)
* change your inflection
* make a gesture

If you are limited to only speaking words, you and your friend need to pick a word ahead of time which means "now I'm speaking a style command".

Is there a word that means "style finished, back to text"?

Also, what happens when those special words themselves appears in the text?

#### One after another

Like a flute playing only one note at a time, *serial communication* means bits of information **must** follow one after another, all traveling down the same wire.

*Parallel communication* is many people talking at once. It's a piano playing more than one note at one time. Like many people talking at once, this kind of communication get complicated fast.

Computers read our .html files character by character, one after another. Imagine the *new lines* are invisible characters, the code becomes one long line of text, like sheet music.

### Peeking inside files: .rtf file format

Make a simple .rtf file that includes:

* a title with a large font
* paragraph text with a scattering of font colors, bold, italics.

Open the .rtf file in Sublime Text. *"Where did all this extra stuff come from?"*

> it's the style

You might think, "this code is meant for the computer, not for me!" But wait, let's take a second and sit with it. Is there anything we can discern?

​                      [ image of a person delivering a letter to a computer "here this is for you" ]

​                     [ image of the computer and person sitting and reading the letter together ]

* the words we typed are hiding between code
* font names
* margins, padding
* colors
* `\b` means bold

Look at how each command starts with a `\` and the command goes until it gets to a space. This is the "say it louder" or "change your inflection" moment.

### Humans and computers speak two different languages

Computer scientists and language designers are doing their best to get computers to speak a human language. They've come a long way. It used to be punch cards, now programming languges are incorporating actual English words.

But they haven't come all the way.

We're going to learn how computers speak so that we can meet them halfway. It not only makes programming a computer a less-stressful task for us, but also when we have these paradigms internalized we can shape our projects in the way that a computer can most maximally attach itself to and more fully explore an idea.

#### Escape Character

In our thought experiment, we invented an "escape word". An escape word invokes an alternative interpretation for the words that come after. Humans speak in words, computers prefer small units: characters. Each individual character gets interpreted and computers use "escape characters".

Today, escape character more typically refers to escaping the escaped, how to make literal what would normally be code, answering from above: "What happens when that word itself appears in the text?"

### Sheet Music

A piece of code is full of line endings and spaces and page-wrapping. Have you ever seen a piece of sheet music laid out in one line?

[ bach keyboard piece in one line ]

It's incredibly inefficient. To solve this we add line breaks that have **nothing to do with the music itself**. The same for code. It's magnitudes more difficult to read a bit of code that is missing all the nice layout and spacing.

This is true for many languages, it's quickly becoming not true for Javascript.

### Summary

* Vocabulary
   * escape character
* We leared the .rtf file format

## 2. HTML & CSS in 10 minutes

> ### DURATION: 30 MINUTES (20 min activity)

### Newspaper layout metaphor

* HTML gives a location and layout to elements
* CSS decorates HTML elements, like font, sizes, color, style

### Element

> `<` and `>`, HTML's answer to the problem from our printing press thought experiment.

This is a tag `<h1>` this is the closing tag `</h1>` - wrap an (1) opening tag and a (2) closing tag around a 3rd thing, like text or an image, and the 3 of them together are called an ELEMENT `<h1>hello, friends</h1>`. void elements don't have closing tags, and are things in themselves. `<br> <img> <input>`. elements show up on the page top left justified, the browser might give them padding and margins.

### Arrangement

Elements attempt to arrange "left to right, top to bottom". Elements stack on the page following 2 rules, elements themselves are one of two *types*:

* *block* elements push the next item (in the code) to sit BELOW them.
* *inline* elements make the next item sit NEXT to it (to the right). (you can of course flip things and make everything right justified).

some block elements: `<p></p>`, `<h1></h1>`, `<div></div>`

some inline elements: `<em></em>`, `<strong></strong>`, `<span></span>`

### Attributes

An element might sometimes needs more information. Consider the element name `<p>` where can you put more information?

> inside the `< >`, after the `p`

* a hyperlink needs to know **where** to take you: `href`
* an image needs to know the filename: `src`

### Invisible Elements

You may have noticed `<div>` or `<span>` these are invisible, why are they useful? A `<span>` can wrap around only a few words of text to change the text color. A `<div>` can mark a section on the page with a different background color.

```html
<p>This is my paragraph but <span>this is the best part</span></p>
```

### CSS

```css
property: value;
property: value;
```

CSS can change color, background-color, font, font-size, adjust padding and margin, placement on the screen.

> each browser comes with a default setting for font sizes, margins, colors, all decisions made by human designers. you can change these.

css the language has a selector followed by curly braces `{ }` if you want to style an `h1 {  }`, 
the entire HTML document: `html { }`
every element on the page `*{ }` (* is a placeholder)
this is the targeting system. we actually have to add code:

stack as many into an `h1{ }` as you want

```css
h1{
  font-size: 12px;
  color: #39F;
  background-color: black;
  border: 2px solid black;
}
```
### Exercise, hyperlink between 2 files

* `<a href="two.html">my link text</a>`
* `<a href="one.html">back to first page</a>`

### Summary

* Vocabulary:
   * element
   * attributes
   * block & inline
* 2 languages: HTML and CSS (HTML isn't *technically* a language)

### Homework #1: Construct a choose your own adventure story with a narrative and hyperlinks that take the reader to new pages with a variety of story endings.

## 3. Javascript

> ### DURATION: 2 HOURS

> * Variables and types:
>    * boolean, string, number
>    * arrays, objects
> * Arithmetic and compare
> * Loops and If statement
> * Functions

Now we get into the **real** programming. The difference, we were only *printing* webpages. We are missing out on using fundamental parts inside the computer:

### Three things computers can do in a computer program

* store stuff (and change it and reuse it)
* arithmetic (and compare numbers)
* control flow (choose your own adventure books)

#### Three languages in one document: HTML, CSS, Javascript

```html
<html>
  <head>
    <style>
    /* css goes here */
    </style>
  </head>
  <body>
    <script>
    // javascript goes here
    </script>
  </body>
</html>
```

## 3a. Javascript: Store Stuff

### `var`, the garden metaphor

"var" stands for "variable".

```javascript
var message = "hello";
```

When the computer sees "var" it's like saying to the computer "we need a spot in memory". So the computer carves out a little spot in memory before it even knows what is going in.

It's like a gardener digging a little hole in the garden. A plant will go there in a moment.

### Three simple things that can be planted

There are 3 simple types of variables that can be stored. Each one has unique properties, for example the computer can do math on the numbers, but it can't do math on words.

* number
* string (words)
* boolean (true or false)

Take a preview of what is ahead. All possible variable types:

### 3, 2, 1 things that can be planted

* **3 fundamental types**: boolean, string, number
* **2 containers**: array, object
* **1 executable**: function

We are going to focus on fundamental types and come back to containers and functions later.

> *Picture the magnetic media and microchips inside your computer, by writing"var" you just claimed some realestate **in there**, how powerful, right?! There are billions of bytes available to you.*

### Variable Names

We made 1 variable. Great! It's easy to keep track of. However, we're going to be writing programs that have 20 of these little holes in our garden. We need to be able to say "this one" and "that one over there".

We need to be able to **name** spots in memory. We can't call different spots in memory the same name. Computers like to be *precise*.

> Remember, computer reads top-down. Saying "`var message`" is **declaring** the variable, it exists from that line and every moment after. But if you tried to ask the computer about it *before* it gets declared, it won't know about it.

*you only have to type "var message" once! after the first time, just type "message"*

#### All Possible Variable Names

> Try naming a variable `var while`. "while" turned red. bad sign! yep, while is a command that does something else. It's a word that has a special use. Try a variable that starts with a number `var 123message`. "123" is purple, this isn't going to work either. But `message123` works. okay so we just learned 2 rules:
>
> 1. there are a few words like 30 words that are reserved, we won't learn them all now, just know they are there.
> 2. can't start a variable with a number.
>
> There are more nuanced rules. Stick with these 2 for now.

### = The Equal Sign

what does equal sign mean in grade school math?

> The values on the one side match are equivalent to the values on the other side, even if they are in different forms.

good! Now, this sucks and I'm sorry. But the meaning of this equal sign has NOTHING to do with that.

```javascript
var message ⬅︎ "hello";
```

when I see the equal sign I think about this arrow. This equal sign means

*take the thing on the right and store it into the variable on the left*.

It's not a "truth statement". It's an *action*. Imagine a steampunk computer that's fully mechanical. This line of code would boot up it's motors and conveyor belts and start to move this digital object into the spot in memory named "message".

### Syntax

```javascript
var message = "hello";
```

This is *one line* of javascript. Many lines of Javascript (but not all) end with a `;` semicolon. Words in Javascript are separated by spaces, and word-order is important. After "`var`" Javascript is expecting a one-word name for the variable.

Javascript is a language, like English, and there are many rules that dictate order: strict rules (the computer crashes) and rules meant for elegance (the computer understands two different approaches to be the same).

### String: the first variable type

This type of variable is called a *string*. String means collection of characters. It can have spaces, and punctuation too. What are some of the wildest characters you can think of?

* punctuation
* numbers, look it can hold numbers
* emojis!

```javascript
var string1 = "123 Robby! #😇✌️😀";
```

Why do we need `" "` marks?

> *so the computer knows we're not writing a variable name! Also we can put spaces in there.*

#### Unicode

The set of all possible characters we can put in a Javascript string is determined by the Unicode Consortium. It's fascinating to look at the specification, the characters listed earliest in the set were at one point the only ones around, and you might notice they are all characters from Latin-based languages. This is a consequence of the designers only thinking about themselves creating an exclusive design. Unicode produces [charts](http://www.unicode.org/charts/) if you are interested.

There is not only a lot of languages but fun symbols too, like box drawing characters.

```
                     ╔════════════════════════════════════════╗
                     ║  ◢◣       Throwback Thursday       ◥◤  ║
                     ╚═══╤════════════════════════════════╤═══╝
                         ├────────────────────────────────┤
                         │                                │
                         │                                │
```

### Number: the second variable type

```javascript
var answer = .25 * 133;
```

### console.log to see inside variables

*"computer, tell me what is inside of you right now"*

console log `answer`, do you notice anything different?

> It's a different color

Numbers are blue. When a number is inside of a string, like `'Robby 123$ !😇✌️😀'` it isn't blue. When it prints a number blue, it's the computer telling us that it recognizes this as a number type, and that it can do *math* on it.

Let's do math:

## 3b. Javascript: Arithmetic

```javascript
var total = 5;
console.log(total + 10);
```

What do you expect, yep, it shows 15 now. What about these lines of code:

```javascript
var total = 5;
console.log(total + 10);
console.log(total);
```

> `15 5` 

See, it doesn't change the value of "total", the little spot in memory still has the number 5.

Now in the same program, down below, let's change the variable:

```javascript
total = 8;
```

console.log total now, what is inside of total now? 8. yes. what happened to the 5?

> *The 5 got replaced*

The 5 no longer exists. we lost it. it is gone from the memory of the computer. 

*The computer can only put 1 thing in a variable spot at a time*

> **Review: why don't you keep writing `var`?**
>
> remember what var does: `var` tells the computer to carve out a little spot in memory. dig a hole in the garden. once that hole exists you can keep using it.

#### Numbers that are secretly strings

*Is it possible to make a string that is a number? "`var stringnumber = "5";`" Yep, not blue! Can't do math on it.*

#### Question: What happens when you add a string and a number?

*"The number turns into a string and is **appended** to the string"*

The plus sign means something different between 2 strings.

```javascript
var first = "Robby";
var last = "Kraft";
var fullname = first + " " + last;
```

### i = i + 1

check out this line of code

```javascript
total = total + 1;
```

console.log "total" now, what do you expect? it's 9 now. 

how does the computer parse this line of code? let's go very slowly

```javascript
total = total + 1;
```

first, locate the = sign. process everything **to the right of the = sign**

```javascript
// everything to the right of the =
total + 1;
// turns into
8 + 1;
// turns into
9;
```

now rewrite the full line with the =

```javascript
total = 9;
```

now this looks familiar! this is going to store 9 into total. We are going to use this trick a lot! `total = total + 1` means:

*"take whatever is in **total** and increment it by 1"*

### Boolean: the third variable type

Do you all remember "greater than" and "less than" symbols from math class?

> `< >`

```javascript
var answer = 5 > 3;
console.log(answer);
```

> it logs "true"!

This is the final type: **boolean**. It can be *true* or *false*.

What color is "true" in the console? It's blue, like the numbers. This is a hint, we can use it for something. And we will, we'll use this later in **if statements** and **loops**.

### Exercise: Dice Roll

Goal: Create an HTML page that generates a random number between 1 and 6.

* New Vocabulary: **integer** and **floating point**
* `Math.random()`, `document.body.innerHTML`

#### Random number generator: `Math.random()`

Console.log it and tell me what you get. Refresh the page. describe this number:

```javascript
console.log( Math.random() );
```

- floating point number
- between 0.0 and 1.0
- about 16 digits long

Remember what we are looking for now. We want a **integer** between **0** and up to but not including **5**. (0, 1, 2, 3, or 4)

```javascript
var randomNumber = Math.random()
```

#### 0.0 to 1.0

Why between 0 and 1? This range is a delight to work with. For example if you want a random number between 0 and 6, all you have to do is multiply the result by 6.

```javascript
var randomNumber = Math.random() * 6;
```

This now gives you a random number between 0.0 and 6.0:

> YES can be 0.0000
>
> NO will never be 6.000, at most it will ever be 5.9999999...

Console.log a random number to see what you get:

```javascript
console.log(randomNumber);
```

> `3.899430910902865`

we want **integers**, we want a 2 or 4 or 0. We can get this from a **floating point** number by asking the computer to truncate the decimal value.

#### turn a float into an int

The command performs a mathematical "floor" operation, it finds the **next lower** integer.

```javascript
parseInt(myFloat)
```

It works like how Math.random() works, you have to store it into another variable.

```javascript
var randomInt = parseInt( Math.random() );
```

or in one line

```javascript
var randomInt = parseInt( Math.random() * 6 );
```

Remember, we want 1,2,3,4,5,6, not 0,1,2,3,4,5

```javascript
var randomInt = parseInt( Math.random() * 6 ) + 1;
```

#### Breaking things out

the line above is the same thing as saying this:

```javascript
var randomFloat = Math.random();
var largerFloat = randomFloat * 6;
var randomInt = parseInt(largerFloat);
var final = randomInt + 1;
```

it's up to you if you like to squeeze everything on one line, or break things out in a more readable fashion.

### Exercise: "What happens when you add a string and a number?"

## 3c. Javascript: Control Flow

Normally the computer reads every line of code, from top to bottom, stopping when it gets to the end. There are different ways we can deviate from this. We can ask the computer to:

* skip over a bit of code, depending on a condition.
* repeat a bit of code over and over.
* make an event (like a button press) cause a bit of code to run.

Let's play with the second one: repeat code over and over.

### `while(){}`

This is a **while loop**:

* it repeats as long as the `( )` is true
* it runs the code inside the `{ }`

```javascript
while(5 < 10){
  console.log("hello");
}
```

the statement `5 < 10` is *always* true. What we made here is an **infinite loop**. 

Run it if you like, but it will **crash** your browser. You can't refresh to recover from it. You have to close the browser tab.

> We need a `( )` statement that is true **some of the time** and eventually becomes false

Any ideas?

watch this, I will put a variable in place of the 5, the variable will change over the course of the loop.

```javascript
var counter = 0;
while(counter < 10){
  console.log("hello");
  counter = counter + 1;
}
```

See what I did there? Let's trace the path of the program. 

* the program begins at the top of the HTML file
* when it gets to the `while(counter < 10){` line it sees "true" so it goes inside the { } and runs that code
* it runs the { } code 10 times until counter is 10. because `while(10 < 10)` is false. 
* when it discovers a false value, it **skips** over the { } this time, goes to the line **just after** the closing } and continues just as usual, running the rest of the program.

### Activity: One million dollars

Let's start small with only 100 loops `while(counter < 100)`, refresh the page, add another zero

```javascript
var counter = 0;
var string = "";
while(counter < 100){
	string = string + "💵";
	counter = counter + 1;
}
document.body.innerHTML = "<h1>" + string + "</h1>";
```

### Activity: Random generated color bars

Let's use the "hue saturation lightness" color space.

```javascript
var counter = 0;
while(counter < 10){
	var d = document.createElement("div");
	var hue = parseInt(Math.random()*360);
	var color = "hsl(" + hue + ", 100%, 50%)";
	d.style.backgroundColor = color;
	document.body.appendChild(d);
	counter = counter + 1;
}
```

### Homework #2: use addition and multiplication from the "dice roll" exercise to limit the colors to a pleasing palette. Add randomly generated numbers to fit in the "saturation" and "lightness" spots too.

### Exercise: 1,000,000 Fibonacci Numbers or fixed-width Sierpinski triangle

## 3a. (again) Javascript: Store Stuff (containers)

We're getting into *real programming*, now we're getting into *real data*.

*Get to know your classmates!*

Okay let's establish a problem. we're going to store our classmates names. just the people around us:

```javascript
var friend1 = "Alessio"
var friend2 = "Leo"
var friend3 = "Vivek"
```

Do you see where this is going? we're having to keep track of all these variable names for a collection of similar objects.

> containers fit in the spot that a variable goes, and can hold unlimited* number of objects.

Remember when I said one spot in memory can only have 1 object - and if you put another thing in that spot it replaces the old thing. This is still true, a spot in memory only holds 1 thing, but now we can kind of cheat and make that 1 thing a "container". This container can hold unlimited things. But if we don't put that container there first, it behaves like it replaces objects.

```javascript
var friends = [];
```

This makes an empty container. We call this container an **array**.

#### Arrays group similar data

Arrays solve a problem (a problem you maybe didn't know existed). Think back about variable names. Remember when we ask the computer for memory, we are required to think up a "name" for this spot in memory. That name should *reflect* what's inside. 

If there are 10 spots in memory all having to do with the same kind of data, it's more cumbersome than helpful to think up individual names for each spot! We should call them all just by 1 thing, and count off to get to each one.

"Can I have the 3rd apple?"

"Take 100 sheets of paper."

There is a group of things. 10 apples. 1,000 sheets of paper, you don't have to think up individual names for each sheet of paper. It's a group. And this brings us to the main device when using arrays:

*We use numbers to point to individual things inside an array.*

### Array

Fill up an array like this: objects separated by commas

```javascript
var friends = ["Alessio", "Leo", "Vivek", "Carolyn", "Simone"];
```

Alternatively, we could have made our array from our old variables

```javascript
var friend1 = "Alessio";
var friend2 = "Leo";
var friend3 = "Vivek";
var friend4 = "Carolyn";
var friend5 = "Simone";

var friends = [friend1, friend2, friend3, friend4, friend5];
```

Finally, if you forget something (or want to add later), use the function "push". This will append it **to the end** of the array. As we will see, **order matters!**

```javascript
var friends = ["Alessio", "Leo", "Vivek", "Carolyn"];
friends.push("Simone");
```

These 3 bits of code result in the same array. The first one is more concise, the second is useful if you need to calculate or modify things before you store them.

Now we can console log the entire array

```javascript
console.log(friends);
```

this is nice but this is showing me the whole container. what if I want to retrieve one particular object from the array. I need to "get it out" of the array. (the original stays in there, it's more like it gives me a copy)

### Problem: how do we "pull out" a variable from an array?

```javascript
var friends = ["Alessio", "Leo", "Vivek", "Carolyn", "Simone"];
```

We have an array of 5 names. It turns out the computer **always** stores them in the same order. you can count on that.

> Give me the *first* object in the array

Try this out: `friends[1]`

* the name of the variable
* square brackets with **an integer** inside: `[4]`

It's the same square bracket as when we declared the variable `var friends = [];` but it has a different meaning. Before, square bracket *created* a container, this time we are *retrieving* from the container

> Like the `+` for numbers and strings, the `[ ]` has 2 different meanings for *declaring* and *retrieving*.

Try to console.log it `friends[1]` 

```javascript
console.log( friends[1] );
```

did it retrieve the first item? nope it gave us the second. 🙃

#### computers start counting from 0

the first item, according to a computer, is item number 0.

```javascript
console.log( friends[0] ); 
```

this prints out `"Alessio"`

> I'm sorry. It's terrible. I know. Computers count from zero. It's annoying to get used to, but it does make things *much* easier later on.

```javascript
var friends = ["Alessio", "Leo", "Vivek", "Carolyn", "Simone"];
```

So with this array it's possible for us to ask for `friends[0]`, `friends[1]`, `friends[2]`, `friends[3]`, `friends[4]`. Stop at the number 4, the 5th item, the last item.

### Activity: Random friend picker

> Goal: we want to make a program that picks a random friend from our friend's array and write it on the page

This means we need the computer to say things like:

```javascript
friends[2];
```

or

```javascript
friends[4];
```

Computers have a thing called random number generators. We want to be able to ask a computer for a random number, and use that random number as the array index:

```javascript
friends[randomNumber];
```

## 4. Functions 

> ### DURATION: 1 HOUR 

Functions are blocks of code that we can package up and forget about. We can call them later, and they are very useful if we find ourselves **repeating code**.

*If you are repeating code:*

1. identify the repeated portions
2. package one instance up in a **function**
3. **call** the function (meaning "run" it) in place of every instance of repeated code

#### ( )

Similar to how arrays use `[ ]`, functions are identified by special characters: parenthesis.

```javascript
myFunctionName()
```

Also similar to arrays, the `( )` have 2 different meanings in 2 different contexts:

* Functions are declared once
* you can run a function an unlimited number of times

The declaration begins with the word "function" and the `( )` are immediately followed by `{ }`. Every line of code **inside the { }** is what runs when you run the function.

```javascript
function myFunctionName(){}
```

Move the typing cursor between the `{ }`, hit *return* and type some lines of code.

```javascript
function sayHello(){
  console.log("hey friend, here is a random number");
  console.log( Math.random() );
}
```

Keep in mind: this function *sayHello* **won't run until you tell it to**. Calling a function looks like this:

```javascript
sayHello();
```

All together now, the declaration and call:

```javascript
function sayHello(){
  console.log("hey friend, here is a random number");
  console.log( Math.random() );
}

sayHello();
```

All that code does the same thing as:

```javascript
console.log("hey friend, here is a random number");
console.log( Math.random() );
```

the advantage to putting it in the function is we can run the code

* whenever we want
* as many times as we want

> function names are followed by `()` that's how the computer knows it's a function instead of a variable.

### Exercise: Random Integer Function

There is one bit of code we've been repeating over and over in our in-class exercises.

> *We keep having to shape random numbers into integers*

Yes! Think about each instance abstractly for a second. Every time:

1. We turn a float into an int `parseInt` and `Math.random()`.
2. the integer is a different range each time; using multiplication and addition.
3. the result gets used in different ways, like as parts of strings or indices of arrays.

If we're being very precise about it only #1 is ever **exactly** duplicated. However, functions provide us with a tool to be able to include small customization each time we run it, to cover #2.

#### Arguments: customize each time we run

Functions have the ability to be customized each time they run. The recipe stays the same, the way they let us do it is you can **put variables inbetween the parenthesis**.

```javascript
function half(num){
    console.log(num / 2);
}
```

See "num" inbetween the parenthesis? That is a variable, it's not visible but it's like the computer is secretly saying:

```javascript
var num
```

You fill the variable with something **everytime you call the function**:

```javascript
half(44);
```

Running this function will set "num" to equal 44 **before** it runs any of the code between the `{ }`.

#### Return: "turn into"

We have secretly been using a function. `Math.random()` is a function that *turns into* a random number. Let's make our own function that turns into a thing:

```javascript
function myName(){
    return "Robby";
}
```

Just like how `Math.random()` turns into a random number, `myName()` will turn into "Robby".

We can change our "half" function to include a return.

```javascript
function half(num){
    return num/2;
}
```

and we call it like this:

```javascript
var halved = half(77);
```

*Let's make a function that generates a random integer between two values and returns it to us*

```javascript
function randomInt(low, high){
  var random = parseInt( Math.random()*(high-low)+low);
  return random;
}
```

### Exercise: Drawing with mouse

```javascript
document.onmousemove = function(event){
  // console.log(event);
  var d = document.createElement("div");
  d.style.backgroundColor = "hsl("+randomInt(200,220)+", 100%, 50%)";
  var width = randomInt(10,100);
  var height = randomInt(10,100);
  d.style.width = width + "px";
  d.style.height = height + "px";
  d.style.top = event.y - height/2 + "px";
  d.style.left = event.x - width/2 + "px";
  document.body.appendChild(d);
}
```



## 3a. (again) Javascript: Store Stuff (Containers)

### Problem: items in arrays have no context

Let's say we ask the internet "what is the temperature right now?" we run some function, and it replies with a number:

```javascript
56.26
```

what if we ask "what is the *weather* right now?" which includes temperature, humidity, chance of rain.

> we need a container

yes. we could get back all 3 numbers in, say, an array

```javascript
[56.26, .1, 0]
```

and those are... what again? temperature, then humidity, then chance of rain, right?

that's the **problem**, we don't know what those number are, they don't have *labels*.

## 5. Data: Javascript Object Notation

> ### DURATION: 45 MINUTES

### Objects, the final container type

Imagine solving our problem with 2 arrays.

```javascript
["temperature", "humidity", "chance of rain"]
[56.26, .1, 0]
```

The first array tells you what are the objects in the second array. There is a better way, and it's called an *object*.

* Arrays use `[]`
* Objects use `{}`

An object ties a **label** to a **variable**. the correct vocabulary is: **key** and **value**.

```javascript
{
  "temperature" : 56.26,
  "humidity" : .1,
  "chance of rain" : 0
}
```

Inside an object, the notation is like this:

1. key
2. colon
3. value
4. comma (unless it is the last line)

```javascript
KEY : VALUE,
```

Commas separate entries, so you don't need one on the last line.

Let's store this into a variable called weather:

```javascript
var weather = {
  "temperature" : 56.26,
  "humidity" : .1,
  "chance of rain" : 0
}
```

### How do we get an item out of an object?

How do we get the temperature value? the 56.26? 

> *Everytime I don't know how to do something, console log something, anything*

```javascript
console.log(weather);
```

Look inside this variable (expand the triangle). If you compare this with console logging an array, there are similarities with a small difference:

* the array lists each entry with a **number** on the left
* the object lists each entry with a **word** to the left

In an array, we get a variable out by putting a **number** in between `[ ]`. In an object, we get variables out putting a **word** in between `[ ]`

```javascript
weather["temperature"]
```

### Arrays inside arrays

Let's revisit arrays for a second:

```javascript
var doublearray = [
  ["apple","pear"],
  ["strawberry", "blueberry"],
  ["potato", "onion"]
]
```

How do I console.log "onion"?

> console.log( doublearray[5] );

try it. nope. it helps if we `console.log(doublearray)`

expand the triangles twice, we have an array inside an array. if we did `doublearray[0]` we get an **array** back. we need to go inside an array inside an array.

```javascript
console.log( doublearray[2][1] )
```

is the same as typing

```javascript
var innerArray = doublearray[2];
console.log( innerArray[1] );
```

look closely! those are the same thing. sometimes it helps to *break things apart* like that.

if we had an array inside an array inside an array, we would stack **three** square brackets

```javascript
triplearray[4][9][1]
```

what is the order? the first `[]` goes inside the first level, the second `[]` goes inside the second level. each step takes you deeper in the arrays

### Objects inside objects

in the same manner, let's put objects inside of an object. let's make a catalog of some of our favorite things: 

* favorite breakfast food
* favorite animal

let's do this for ourselves, and for our neighbors.

```javascript
var classmates = {
  "Robby" : (our object will go here)
}
```

keys will be the names of the students. let's fill out the object for ourselves:

```javascript
var classmates = {
  "Robby" : {
    "color" : "#0066FF",
    "animal" : "elephant"
  }
}
```

The value of "Robby" is an object. inside that object, the value of "breakfast" is "scrambled eggs".

How do I get "elephant"?

```javascript
classmates["Robby"]["animal"]
```

Let's add a few more students

```javascript
var classmates = {
  "Robby" : {
    "color" : "#0066FF",
    "animal" : "elephant"
  },
  "Leo" : {
    "color" : "black",
    "animal" : "scorpion"
  },
  "Alessio" : {
    "color" : "#C08020",
    "animal" : "squirrel"
  }
}
```

Notice the lines with `},` we need to put commas between entries. it's easier to see if the object was brief and fit on one line:

```javascript
{
  "Robby" : {"hours" : 5},
  "Leo" : {"hours" : 3},
  "Alessio" : {"hours" : 8}
}
```

The last one is the only one without a comma.

console.log our classmates variable, and look at how the object keys are sorted alphabetically.

#### Order is not maintained in objects, unlike arrays

Variables inside an object don't have a numerical position. There is no order. They just exist under the "key".

### Real weather data from the internet

> Most of the data that gets passed around on the internet **is a Javascript object** (.json file stands for "Javascript object notation")

Check out this minified .json file response from a weather api.

what do you see?

*"objects, numbers, strings, arrays"*

Run the .json through a formatter / beautifier. All this does is add "whitespace" (carriage returns, spaces) to make it more readable.

How do we get at some of the data that is *deep*?

```javascript
weather["current"]["hourly"][0]["precip"]
```

I pre-downloaded this file. Asking the internet for data takes a little bit of knowledge and code. Fortunately for us, there is an elegant library that has been around for a long time and is pretty ubiquitous at this point:

### JQuery

JQuery is a set of javascript functions that someone wrote (his name is John and he lives here in New York). It's easy to include into your html file, just add this line at the top:

```html
<!DOCTYPE html>
<html>
  <head>
    <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
  </head>
  <body>    
  </body>
</html>
```

Now we can use JQuery anywhere in our `<script>` section.

JQuery makes getting data from the internet *really* simple, it's just one line of code:

```javascript
$.getJSON( url, function(data){ } );
```

"Calling JQuery" is typing a `$`. It's like saying Math.random(). The random function is inhabiting this library called "Math". getJSON is inhabiting this library called `$` (that's a joke, it's called JQuery).

getJSON function has 2 *arguments* or *parameters*:

- **the url** (string)
- **the callback** (function)

the url is expecting at the other end is some kind of data file: .json, .csv, .txt even. Type this URL into a browser bar to make sure it pulls up data.

> using an API's url is neat because before you make the call *there is no file at the other end*, instead, the server generates one in realtime.

#### the callback function

Think in terms of nanoseconds and follow the computer as it reads each line:

1. starts at the top, gets to the `$.getJSON(...` part and asks the server for data.
2. it skips over everything inside of the `function(data){}` and continues running everything **after** the end of the function.
3. an eternity of nanoseconds pass
4. the server finally gets back to us and the pointer goes back up to the `function(data){ }` and runs everything inbetween the `{ }`.

in review, your computer reads your program in this order:

1. top to bottom, but skip over the callback
2. when file is downloaded, go back and run everything *only inside* the callback.

### Exercise: Fetch a JSON

Let's try to fetch a .json from an API. The Citibike API at the moment is free and doesn't require a key. Here is the URL:

```
"https://api.citybik.es/v2/networks/citi-bike-nyc"
```

Let's grab the data, console.log it, and see if we can find a station nearby.

### Exercise: Make our own JSON

Create a .json file that is your-name.json which will contain information about you. Read carefully to make sure content is structured uniformly. 

The top level will contain 3 keys: **name**, **home**, **color**:

```javascript
{
    "name" : ["Robby", "Kraft"],
    "home" : {"latitude":40, "longitude":-74},
    "color" : "#0066FF"
}
```

* **name** should be an array of strings.
* **home** should be an object with 2 keys, latitude and longitude, each value is a number. This is the location you come from or wherever you call home.
* **color** should be your favorite color, or just a color you like right now, as a 6-digit hex string.

when you are done

1. Validate your .json file: [jsonformatter.curiousconcept.com](jsonformatter.curiousconcept.com)
2. Upload your .json to your github. 
3. place a link to your .json file in our class shared document.

### Exercise: Print everyone's names in their favorite color

prerequisite: watch a while loop turn into a for loop

this:

```javascript
var i = 0;
while(i < 20){
    i = i + 1;
}
```

is the same as:

```javascript
for(var i = 0; i < 20; i = i + 1){
}
```

so much nicer, right?!

#### Objective 1: download 20 .json files, add each of the contents as an entry in a "classmates" array

```javascript
var urls = [ ... ];
var classmates = [];
for(var i = 0; i < urls.length; i = i + 1){
  $.getJSON(urls[i], function(data){
    classmates.push(data);
    if(classmates.length == urls.length){
      downloadComplete();
    }
  });
}
```

#### Objective 2: print every classmate's name onto the page

```javascript
function downloadComplete(){
  for(var i = 0; i < classmates.length; i = i+1){
    var p = document.createElement("p");
    p.innerHTML = classmates[i].name[0];
    p.style.color = classmates[i].color;
    document.body.appendChild(p);
  }
}
```

### Homework: Wrap a hyperlink around each of our classmate's names that links to a Google Map centered on the person's latitude and longitude

Navigate to [maps.google.com](maps.google.com) and drag the map around, see how the latitude and longitude is in the URL bar?

```
https://www.google.com/maps/@40.706195,-73.9905063,13z
```

You can manually make a link to a google map location by writing the URL:

```javascript
var url = "https://www.google.com/maps/@" + lat + "," + lon + ",13z
```

### Optional Exercise: Our class on Google Maps

If we have enough time, this is a great exercise to do as a class.

Use this Google Maps API Key

```html
<script src="https://maps.googleapis.com/maps/api/js?key=***************************************&callback=getData"></script>
```

If we're short on time, use this template for the HTML page:

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
    #map{
      width:100%;
      height:500px;
    }
    </style>
    <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
  </head>
  <body>

    <div id="map"></div>

    <script src="https://maps.googleapis.com/maps/api/js?key=***************************************&callback=getData"></script>

  </body>
</html>
```

and drop this `<script>` section

```javascript
function downloadComplete(){
  var options = {
    center: new google.maps.LatLng(40, -74),
    zoom : 5
  };
  var map = new google.maps.Map(document.getElementById("map"), options);
  for(var i = 0; i < classmates.length; i = i + 1){
    var lat = classmates[i].home.latitude;
    var lon = classmates[i].home.longitude;
    var marker = new google.maps.Marker({position: new google.maps.LatLng(lat, lon)});
    marker.setMap(map);
  }
}
```

## 6. Generative Content

> ### DURATION: 45 MINUTES

### Markov Chain

If you aren't already familiar with [Project Gutenberg](https://www.gutenberg.org/), try "browse catalog" and take a look around. Everyone select a book. Download "Plain Text UTF-8" format. This gives you a .txt file.

Let's get our HTML ready to upload a file. This is a file upload dialog:

```html
<input type="file">
```

Give it an "id" attribute. Your HTML page should look like this:

```html
<!DOCTYPE html>
<html>
  <body>
    <input type="file" id="file-input">
  </body>
</html
```

Add this bit of Javascript to capture the event of the user uploading a document:

```javascript
document.getElementById("file-input").onchange = function(){
  reader.readAsText(this.files[0]);
}
var reader = new FileReader();
reader.onload = function(e) {
  console.log(reader.result);
}
```

When the user presses the "Choose File" button and selects a file, the "onchange" function runs, calling the FileReader, which calls the "onload" function once all the bytes of the files are uploaded into the HTML page.

`console.log(reader.result)` prints out the text contents of the file you just uploaded!

#### Home stretch: Sort the text into a Markov dictionary

Let's stick everything else into a function called "generatePoem" with one argument: the input text.

```javascript
function generatePoem(text){
  var words = text.split(/\s+/);
  console.log(words);
}
```

This magical line (regular expressions, check them out!) turns one big block of text into an array of words, having separated them by newlines and spaces.

The next step gets at the heart of what a Markov chain is. We are going to build an object where each key is a word in the document. Undoubtably, words will appear more than once. The value associated with each key (remember each key is a word in the text) is an array of words **that follow the word in the source text**. 

So for example, the word "carefully" appears 11 times and is followed by a unique word each time:

```javascript
["provided", "shut", "aimed,", "in", "watched", "so", "among", "noted", "took", "studying", "about"]
```

Here is the code to build a Markov dictionary:

```javascript
function generatePoem(text){
  var words = text.split(/\s+/);

  var dictionary = {};
  for(var i = 0; i < words.length-1; i = i + 1){
    var word = words[i];
    var nextword = words[i+1];
    if(dictionary[word] == undefined){
      dictionary[word] = [];
    }
    dictionary[word].push(nextword);
  }
  console.log(dictionary);
}
```

Once we get this, all we need is a seed word, one random word from the text and we can generate content like this:

1. ask the Markov dictionary for the array of words for the seed word. ("carefully" will give you 11 words)
2. choose a word at random from this list of words (remember these are words that follow the seed word)
3. this selected word becomes your new seed word, go back to step 1. repeat as many times as you like.

```javascript
var startword = words[ parseInt( Math.random() * words.length ) ];
var phrase = [ startword ];
for(var i = 0; i < 100; i++){
  var word = phrase[i];
  var nextwords = dictionary[word];
  var nextword = nextwords[ parseInt(Math.random()*nextwords.length) ];
  phrase.push(nextword);
}
```

Ask the computer to print the result and read it out loud. It sounds really weird! The generative algorithm has no concept of language, there is no linguistic cohesion, but it does obey local rules. It's a peek into a world of a computer attempting (very poorly) to learn. And occasionally the turn of phrases it comes up with are wicked clever.

From Jule's Verne's 20,000 Leagues Under the Sea

> *I want to the status of all my eyes!*

or

> *they must come for every sail freely. To my head got a culpable action, a seaweed which kept at the surface of this basin of the globe the wire of the full refund from my great rapidity. I could not be the Nautilus was sensible advice*

or

> *That is nothing but in the water in perfect negative.*
