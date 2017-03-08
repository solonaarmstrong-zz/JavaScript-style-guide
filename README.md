# JavaScript Style Guide

*An approach to JavaScript, amalgamated from a few sources, peppered with my own preferences.*

## Table of Contents

## Formatting

<a name="formatting-tabs"></a>
- [1.1](#formatting-tabs) **Tabs**
+ Use tab size 4 for each line indent.
+ Do not use 4 spaces.

```javascript
// good
function(name) {
	// do something;
}
```

<a name="formatting-trailing-whitespace"></a>
- [1.2](#formatting-trailing-whitespace) **No Trailing Whitespace**
No trailing whitespace at the end of a line.

<a name="formatting-chars"></a>
- [1.3](#formatting-chars) **Maximum 100 Characters**
+ Lines should be a maximum of 100 characters long.
+ Long lines should be broken up after operators or natural divisions.

<a name="formatting-semicolons"></a>
- [1.4](#formatting-semicolons) **Use Semicolons**

<a name="formatting-leading-commas"></a>
- [1.5](#formatting-leading-commas) **No leading commas**

```javascript
// bad
const greens = [
	  item1: 'first'
	, item2: 'second'
	, item3: 'third'
];

// good
const array = [
	item1: 'first',
	item2: 'second',
	item3: 'third'
];
```

<a name="formatting-quotes"></a>
- [1.6](#formatting-quotes) **Quotes**
+ Use single quotes.
+ Exception: Don't escape single quotes, use double quotes.

```javascript
// bad
const foo = "bar";

// good
const foo = 'bar';

// good
const foo = "Don't feed the bar";
```

<a name="formatting-braces"></a>
- [1.7](#formatting-braces) **Braces**
+ Opening braces go on the same line, with one space.
+ Closing braces go on their own line.
+ Line up closing braces with the original corresponding line.

```javascript
// bad
function(name)
{
	// do something
}

// good god, no
function(name) 			{
	if(condition) 		{
		// do something
}
}

// good
function(name) {
	if(condition) {
		// do something
	}
}
```

<a name="formatting-case"></a>
- [1.8](#formatting-case) **Case**
+ Classes: CapitalizedWords
+ Variables and Functions: camelCase
+ Constants: UPPER_CASE_WITH_UNDERSCORES
+ Backend
+ Client-side

```javascript
// Classes
const MyClass = ...

// Variables and Functions
const myVariable = ...
const myFunction()...

// Constants 
```



## Variables

<a name="variables-declaration"></a>
- [2.1](#variables-declaration) **Declaration**
+ Use const or let to declare variables.
+ Don't use var to avoid reassigning references.
+ Use let if reassigning references.
+ Avoid declaring global variables when unnecessary.
+ Declare variables on a new line.
+ Group variable types together.

```javascript
// bad
var a = 1;

// good
const a = 1;

// bad
var count = 0;
if(true) {
	count += 1;
}

// good
let count = 0;
if(true) {
	count += 1;
}

// bad
count a = 1;
let count = 0;
count b = 2;

// good
count a = 1;
count b = 2;

let count = 0;

```





Avoid using unary increments.
	//bad

	num++

	//good

	num +- 1



1.3 Conditionals and Loops
Space after keyword and space before brace.
No spaces before or after parentheses.

Operators

Always use ===


