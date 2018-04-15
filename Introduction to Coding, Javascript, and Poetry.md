# Introduction to Coding, Javascript, and Poetry

### May 7, The Metropolitan Library Council of New York

## Program Outline

1. "What is code?"
2. HTML and CSS
3. Javascript
  * Storage
  * Arithmetic
  * Control Flow
4. Functions
   * Event Handlers
   * Callbacks
5. Data: JSON
6. Generative Systems

### Summary of in-class exercises

* Hyperlink between 2 HTML pages
* Dice roll
* Random friend picker
* Generative color swatch
* Sierpinski Triangle
* Drawing with the mouse
* Create a JSON
* Classmates on Google Maps
* Markov-chain poetry

### Summary of homework assignments

* Non-linear Narrative: Choose your own Adventure

### Student prep

1. Create one folder (anywhere on your computer), this will house all our files.
2. Create an account with Github.

### Teacher prep

1. Create a shared doc, and share the link with the class.

### Software

* [Sublime Text](http://www.sublimetext.com)
* [Chrome Browser](http://www.google.com/chrome/)

---

# Sessions

## 1. Introduction: what is code?

> ### DURATION: 15 MINUTES

### Thought experiment

You and your friend are running a printing press. you read the text, they assemble the punches. How do you say to your friend "now switch to bold"?

* say it louder (change volume)
* change your inflection
* make a gesture

### Peeking inside files: .rtf file format

make a simple .rtf file, open it up in sublime. *"Where did all this extra stuff come from?"*

> it's the style

it looks like computer code, right? My first impulse is to say "this is unreadable, and meant for the computer". But let's take a second and sit with it. Is there anything we can recognize?

* colors
* fonts
* margins, padding
* `\b` means bold

look at how each command starts with a `\` and the command goes until it gets to a space. this is the "say it louder" or "change your inflection" moment.

### *Conclusion*: humans and computers speak 2 different languages.

Computer designers and computer scientists are doing their best to get computers to speak human. they've come a long way. it used to be punch cards, now programming languge uses English.

but they haven't come all the way.

we are going to learn how computers speak so that we can meet them halfway. it's not because it makes the computer happier, but it makes us happier, it makes things easier on us when we shape our projects in the way that a computer can attach very easily.

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

* Vocabulary
  * element
  * attributes
  * block & inline
* 2 languages: HTML and CSS (HTML isn't *technically* a language)

### Homework #1: Construct a choose your own adventure story with a narrative and hyperlinks that take the reader to new pages with a variety of story endings.

## 3. Javascript

> ### DURATION: 1 HOUR 30 MINUTES

> * Variables and types:
>   * boolean, string, number
>   * arrays, objects
> * Arithmetic and compare
> * Loops and If statement
> * Functions

Now we get into the **real** programming. The difference, we were only *printing* webpages. We are missing out on using fundamental parts inside the computer:

### 3 things computers can do in a program:

* store stuff (and change it and reuse it)
* arithmetic (and compare numbers)
* control flow (choose your own adventure books)
  * loops
  * if statement

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

### `var` garden metaphor

> dig a hole, plant can go in it

### the 5 things that can be planted

**fundamental types**

* boolean
* string
* number

**collections of things**

* array
* object

> you only have to type "var myvar" once!
> after, just type "myvar"

discuss **fundamental** types before **collections**.

"var" stands for "variable".

```javascript
var message = "hello";
```

when the computer sees "var" it's like saying to the computer "we need a spot in memory". So the computer carves out a little spot in memory before it even knows what is going in.

It's like a gardener digging a little hole in the garden. A plant will go there in a moment.

### Variable Names

We're going to write programs that have 20 of these little holes in our garden. We need to be able to say "this one" and "that one over there".

We need to be able to **name** spots in memory.

> remember, computer reads top-down. Saying `var message` is **declaring** the variable, it exists from that line and every moment after. But if you tried to ask the computer about it *before* it gets declared, it won't know about it.

### = The Equal Sign

what does equal sign mean in grade school math?

> The values on the one side match are equivalent to the values on the other side, even if they are in different forms.

good! Now, this sucks and I'm sorry. But the meaning of this equal sign has NOTHING to do with that.

```javascript
var message ⬅︎ "hello";
```

when I see the equal sign I think about this arrow. This equal sign means

*take the thing on the right and store it into the variable on the left*.

It's not a "truth statement". It's an *action*. If the computer was mechanical, it would boot up it's motors and conveyor belts and start to move this digital object into the spot in memory named "message".

### All Possible Variable Names

> Try naming a variable `var while`. "while" turned red. bad sign! yep, while is a command. it's a word that has a special use. Try a variable that starts with a number `var 123message`. "123" is purple, this isn't going to work either. But `message123` works. okay so we just learned 2 rules:
>
> 1. there are a few words like 30 words that are reserved, we won't learn them all now, just know they are there.
> 2. can't start a variable with a number.
>
> There are more nuanced rules. Stick with these 2 for now.

### Strings

This type of variable is called a *string*. String means collection of characters. It can have spaces, and punctuation too. What are some of the wildest characters you can think of?

* punctuation
* numbers, look it can hold numbers
* emojis!

```javascript
var string1 = 'Robby 123$ !😇✌️😀';
```

Why do we need `" "` marks?

> so the computer knows we're not writing a variable name!

### Number

```javascript
var answer = .25 * 133;
```

### console.log to see inside variables

*"computer, tell me what is inside of you right now"*

console log `answer`, do you notice anything different?

> It's a different color

numbers are blue. when a number is inside of a string, like `'Robby 123$ !😇✌️😀'` it isn't blue. This variable is a number, the computer recognizes that it can do *math* on it.

let's do math:

## 3b. Javascript: Arithmetic

```javascript
var total = 5;
console.log(total + 10);
```

what do you expect, yep, it shows 15 now. What about these lines of code:

```javascript
var total = 5;
console.log(total + 10);
console.log(total);
```

`15 5` See, it doesn't change the value of "total", the little spot in memory still has the number 5.

Now in the same program, down below, let's change the variable:

```javascript
total = 8;
```

console.log total now, what is inside of total now? 8. yes. what happened to the 5?

> The 5 got replaced

The 5 no longer exists. we lost it. it is gone from the memory of the computer. 

*The computer can only put 1 thing in a variable spot at a time*

> **why don't you keep writing `var`?**
> 
> remember what var does: `var` tells the computer to carve out a little spot in memory. dig a hole in the garden. once that hole exists you can keep using it.

### i = i + 1

check out this line of code

```
total = total + 1;
```

console.log total now, what do you expect? it's 9 now. 

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

### boolean

```javascript
var answer = 5 < 3;
console.log(answer);
```

> it logs "true"!

this is the final type **boolean** we will use this later in **if statements** and **loops**

### Exercise: Dice Roll

Introduce

* `Math.random()`
* document.body.innerHTML

### Exercise: "What happens when you add a string and a number?"

## 3c. Javascript: Control Flow

> ### DURATION:

### `while(){}`

this is a while loop

* it repeats as long as the `( )` is true
* it runs the code inside the `{ }`

```
while(5 < 10){
  console.log("hello");
}
```

the statement `5 < 10` is *always* true. What we made here is an **infinite loop**. 

Run it if you like, but it will **crash** your browser. You can't refresh to recover from it. You have to close the browser tab.

> We need a `( )` statement that is true **some of the time** and eventually becomes false

Any ideas?

watch this, I will put a variable in place of the 5, the variable will change over the course of the loop.

```
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

### Activity: Random generated color bars

### Exercise: 1,000,000 Fibonacci Numbers or fixed-width Sierpinski triangle

## 3a. (again) Javascript: Store Stuff (containers)

*Get to know your classmates!*

okay let's establish a problem. we're going to store our classmates names. just the people around us:

```
var friend1 = "Alessio"
var friend2 = "Leo"
var friend3 = "Vivek"
```

do you see where this is going? we're having to keep track of all these variable names for a collection of similar objects.

> containers fit in the spot that a variable goes, and can hold unlimited* number of objects.

Remember when I said one spot in memory can only have 1 object - and if you put another thing in that spot it replaces the old thing. This is still true, a spot in memory only holds 1 thing, but now we can kind of cheat and make that 1 thing a "container". This container can hold unlimited things. But if we don't put that container there first, it behaves like it replaces objects.

```
var friends = [];
```

this makes an empty container. we call this container an array.

### Array

fill up an array like this: objects separated by commas

```
var friends = ["Alessio", "Leo", "Vivek", "Carolyn", "Simone"];
```

alternatively, we could have made our array from our old variables

```
var friend1 = "Alessio";
var friend2 = "Leo";
var friend3 = "Vivek";
var friend4 = "Carolyn";
var friend5 = "Simone";

var friends = [friend1, friend2, friend3, friend4, friend5];
```

both of these have the same effect. the first one is more concise, the second approach is useful if you need to calculate or modify things before you store them.

now we can console log the entire array

```
console.log(friends);
```

this is nice but this is showing me the whole container. what if I want to retrieve one particular object from the array. I need to "get it out" of the array. (the original stays in there, it's more like it gives me a copy)

### Problem: how do we access 1 of the objects in the array?

```
var friends = ["Alessio", "Leo", "Vivek", "Carolyn", "Simone"];
```

we have an array of 5 names. it turns out the computer **always** stores them in the same order. you can count on that.

> Give me the *first* object in the array

Try this out: `friends[1]`

* the name of the variable
* square brackets with a number inside: `[4]`

It's the same square bracket as when we declared the variable `var friends = [];` but it has a different meaning. Before, square bracket *created* a container, this time we are *retrieving* from the container

Try to console.log it `friends[1]` 

```
console.log( friends[1] );
```

did it retrieve the first item? nope it gave us the second.

### computers start counting from 0

the first item, according to a computer, is item number 0.

```
console.log( friends[0] ); 
```

this prints out `"Alessio"`

> I'm sorry. It's terrible. I know. Computers count from zero. It's annoying. We have to deal with it. (it does make things *much* easier later on)

So with our array

```
var friends = ["Alessio", "Leo", "Vivek", "Carolyn", "Simone"];
```

So with this array it's possible for us to ask for `friends[0]`, `friends[1]`, `friends[2]`, `friends[3]`, `friends[4]`. Stop at the number 4, the 5th item, the last item.

## Activity: Random friend picker

> Goal: we want to make a program that picks a random friend from our friend's array and write it on the page

This means we need the computer to say things like:

```
friends[2];
```

or

```
friends[4];
```

Computers have a thing called random number generators. We want to be able to ask a computer for a random number, and use that random number as the array index:

```
friends[randomNumber];
```

### Random number generator: `Math.random()`

Console.log it and tell me what you get. Refresh the page. describe this number:

```
console.log( Math.random() );
```

* floating point number
* between 0.0 and 1.0
* about 16 digits long

Remember what we are looking for now. We want a **integer** between **0** and up to but not including **5**. (0, 1, 2, 3, or 4)

```
var randomNumber = Math.random()
```

### 0.0 to 1.0

This range is a delight to work with. For example if you want a random number between 0 and 5, all you have to do is multiply the result by 5.

```
var randomNumber = Math.random() * 5;
```

this now gives you a random number between 0.0 and 5.0, not including 5.0, so it's possible to get 4.99999.

```
console.log(randomNumber);
```

and you'll see a number like `3.899430910902865`

we want **integers**, we want a 2 or 4 or 0. We can get this from a floating point number by asking the computer to truncate the decimal value.

### turn a float into an int

The command we're looking for is

```
parseInt(myFloat)
```

It works like how Math.random() works, you have to store it into another variable.

```
var myInt = parseInt(myFloat);
```

alternatively if you want to keep things simple and just use one variable write it like this:

```
var myNumber = parseInt(myNumber);
```

remember order of operations: computers read everything to the **right** of the `=` sign first, then stores the result. 

* it takes your `myNumber`, chops off everything past the decimal value
* stores the new result back into `myNumber`

we can do this with our random value:

```
var randomNumber = Math.random() * 5;
randomNumber = parseInt(randomNumber);
```

or in one line

```
var randomNumber = parseInt( Math.random() * 5 );
```

Now we are getting a random integer: 0, 1, 2, 3, or 4. We can write our program!

```
var randomNumber = parseInt( Math.random() * 5 );
var randomStudent = friends[randomnumber];
document.body.innerHTML = randomClassmate;
```

Each time you refresh the page, you get a random name!

## Functions 

> ### DURATION: 

Functions are blocks of code that we can package up and forget about.

### Exercise: Drawing with mouse

```
function randomInt(low, high){
	var random = parseInt( Math.random()*(high-low)+low);
	return random;
}
```

```
function randomBlueColor(){
	return "hsl("+randomInt(200,220)+", 100%, 50%)";
}
```

```
document.onmousemove = function(event){
	// console.log(event);
	var d = document.createElement("div");
	d.style.backgroundColor = randomBlueColor();
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

# objects

what makes an array unique from other variables?

> it's a container

we are going to learn one more container type

## items in arrays have no context

let's say we ask the internet "what is the temperature right now?" we run some function, and it replies with a number:

```
56.26
```

what if we ask "what is the *weather* right now?" which includes temperature, humidity, chance of rain.

> we need a container

yes. we could get back all 3 numbers in, say, an array

```
[56.26, .1, 0]
```

and those are... what again? temperature, then humidity, then chance of rain, right?

that's the **problem**, we don't know what those number are, they don't have *labels*.

### review

how do we get a thing out of an array?

```
var weather = [56.26, .1, 0];
```

we use `[]` and what goes in the `[]`, **a number**. Start counting from 0.

```
console.log( weather[0] );
```

will console log `56.26`.

## objects

imagine solving our problem with 2 arrays.

```
["temperature", "humidity", "chance of rain"]
[56.26, .1, 0]
```

the first array tells you what are the objects in the second array.

there is a better way, and it's called an *object*.

* Arrays are inside `[]`
* Objects are inside `{}`

an object ties a **label** to a **variable**. the correct vocabulary is: **key** and **value**.

```
{
  "temperature" : 56.26,
  "humidity" : .1,
  "chance of rain" : 0
}
```

inside an object, the notation is like this:

1. key
2. colon
3. value
4. comma (unless it is the last line)

```
KEY : VALUE,
```

commas separate entries, so you don't need one on the last line.

let's store this into a variable called weather:

```
var weather = {
  "temperature" : 56.26,
  "humidity" : .1,
  "chance of rain" : 0
}
```

### how do we get an item out of an object?

how do we get the temperature value? the 56.26?

well, console.log weather. and console log an array too

```
console.log(anArray);
console.log(weather);
```

look inside these entries (expand the triangle), notice how the array has numbers on the left side. We get variables out of an array by using these numbers. Same, we get variables of an object using those WORDS

```
weather["temperature"]
```

## arrays inside arrays

let's revisit arrays for a second:

```
var doublearray = [
	["apple","pear"],
	["strawberry", "blueberry"],
	["potato", "onion"]
]
```

how do I console.log "onion"?

> console.log( doublearray[5] );

try it. nope. it helps if we `console.log(doublearray)`

expand the triangles twice, we have an array inside an array. if we did `doublearray[0]` we get an **array** back. we need to go inside an array inside an array.

```
console.log( doublearray[2][1] )
```

is the same as typing

```
var innerArray = doublearray[2];
console.log( innerArray[1] );
```

look closely! those are the same thing. sometimes it helps to *break things apart* like that.

if we had an array inside an array inside an array, we would stack **three** square brackets

```
triplearray[4][9][1]
```

what is the order? the first `[]` goes inside the first level, the second `[]` goes inside the second level. each step takes you deeper in the arrays

## objects inside objects

in the same manner, let's put objects inside of an object. let's make a catalog of some of our favorite things: 

* favorite breakfast food
* favorite animal

let's do this for ourselves, and for our neighbors.

```
var classmates = {
	"Robby" : (our object will go here)
}
```

keys will be the names of the students. let's fill out the object for ourselves:

```
var classmates = {
	"Robby" : {
		"breakfast" : "scrambled eggs",
		"animal" : "elephant"
	}
}
```

The value of "Robby" is an object. inside that object, the value of "breakfast" is "scrambled eggs".

how do I get "elephant"?

```
classmates["Robby"]["animal"]
```

let's add a few more students

```
var classmates = {
	"Robby" : {
		"breakfast" : "scrambled eggs",
		"animal" : "elephant"
	},
	"Leo" : {
		"breakfast" : "bagel with cream cheese",
		"animal" : "scorpion"
	},
	"Alessio" : {
		"breakfast" : "juice",
		"animal" : "squirrel"
	}
}
```

notice the lines with `},`, we need to put commas between entries. it's easier to see if the object was brief and fit on one line:

```
{
	"Robby" : {"a":5},
	"Leo" : {"a":3},
	"Alessio" : {"a":8}
}
```

the last one is the only one without a comma.

console.log our classmates variable, and look at how the object keys are sorted alphabetically.

### order is not a property of objects. only arrays

variables inside an object don't have a numerical position. there is no order. they just exist under the "key".

