# JavaScript Style Guide

*JavaScript best practices, amalgamated from a few sources, peppered with my own preferences.*

## Table of Contents

1. [Formatting](#formatting)  
  [1.1 - Tabs](#formatting--tabs)  
  [1.2 - No Trailing Whitespace](#formatting--trailing-whitespace)  
  [1.3 - Maximum 100 Characters](#formatting--chars)  
  [1.4 - Use Semicolons](#formatting--semicolons)  
  [1.5 - No leading commas](#formatting--leading-commas)  
  [1.6 - Quotes](#formatting--quotes)  
  [1.7 - Braces](#formatting--braces)  
  [1.8 - Spaces](#formatting--spaces)  
  [1.9 - Case](#formatting--case)  
  [1.10 - Spelling Counts](#formatting--spelling)
1. [Comments](#comments)
  [2.1 - Use `//` for single line comments](#comments--single)  
  [2.2 - Indent single line comments with their respective lines of code](#comments--indent)  
  [2.3 - Begin all single line comments with a space](#comments--space)  
  [2.4 - Use `/** ... */` for multiple line comments](#comments--multiple)  
1. [Variables](#variables)
  [3.1 - Declaration](#variables--declaration)  
1. [Objects](#objects)
  [4.1 - Use the literal syntax for object creation](#objects--no-new)  
1. [Arrays](#arrays)
  [5.1 - Use the literal syntax for array creation](#arrays--literals)  
  [5.2 - Use Array push](#arrays--push)  
1. [Conditionals and Loops](#conditionals)
  [6.1 - Use `===` insead of `==` and `!==` instead of `!=`](#conditionals--operators)  
  [6.2 - Use shortcuts for booleans, but explicit comparisons for strings and numbers](#conditionals--shortcuts)  
  [6.3 - Use braces to create blocks](#conditionals--switch-blocks)  
1. [Events](#events)
  [7.1 - When attaching data payloads to events , pass a hash instead of a raw value](#events--hash)  
1. [jQuery](#jquery)
  [8.1 - Prefix jQuery object variables with a `$`](#jquery--dollar-prefix)  
  [8.2 - Cache jQuery lookups](#jquery--cache)  
1. [Resources](#resources)

## Formatting

<a name='formatting-tabs'></a><a name='1.1'></a>
- [1.1](#formatting-tabs) **Tabs**
+ Use tab size 4 for each line indent.
+ Do not use 4 spaces.

	```javascript
	function (name) {
		// do something;
	}
	```

<a name='formatting--trailing-whitespace'></a><a name='1.2'></a>
- [1.2](#formatting-trailing-whitespace) **No Trailing Whitespace**
No trailing whitespace at the end of a line.

<a name='formatting--chars'></a><a name='1.3'></a>
- [1.3](#formatting-chars) **Maximum 100 Characters**
Lines should be a maximum of 100 characters long.
Long lines should be broken up after operators or natural divisions.
Strings that cause the line to go over 100 characters should **not** be written across multiple lines.

	 ```javascript
	 // bad
	 const longString = 'This is a super long message that is very hard to read \
	 because it has been broken up onto several lines. This also makes it \
	 difficult to search. Keep it all on one line, please.';

	 // good
	 const longString = 'This is a super long message that might cause horizontal scrolling, because it is all on one line. But, it is much more searchable and easier to work with.';

<a name='formatting--semicolons'></a><a name='1.4'></a>
- [1.4](#formatting-semicolons) **Use Semicolons**

	```javascript
	// bad
	const variableName = 'value'

	// good
	const variableName = 'value';
	```

<a name='formatting--leading-commas'></a><a name='1.5'></a>
- [1.5](#formatting-leading-commas) **No leading commas**

	```javascript
	// bad
	const array = [
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

<a name='formatting--quotes'></a><a name='1.6'></a>
- [1.6](#formatting-quotes) **Quotes**
Use single quotes.
Exception: Don't escape single quotes, use double quotes.

	```javascript
	// bad
	const foo = "bar";

	// good
	const foo = 'bar';

	// good
	const foo = "Don't feed the bar";
	```

<a name='formatting--braces'></a><a name='1.7'></a>
- [1.7](#formatting-braces) **Braces**
Opening braces go on the same line, with one space.
Closing braces go on their own line.
Line up closing braces with the original corresponding line.

	```javascript
	// bad
	function (name)
	{
		// do something
	}

	// very bad
	function (name) 		{
		if (condition) 		{
			// do something
	}
	}

	// good
	function (name) {
		if (condition) {
			// do something
		}
	}
	```

<a name='formatting--spaces'></a><a name='1.8'></a>
- [1.8](#formatting-spaces) **Spaces**
Space after keyword and space before brace.

	```javascript
	// bad
	function(name){
		// do something
	}

	// good
	function (name) {
		if (condition) {
			// do something
		}
	}
	```

<a name='formatting--case'></a><a name='1.9'></a>
- [1.9](#formatting-case) **Case**
Use camelCase for Variables, Functions, and Instances

	```javascript
	// good
	const variable = ...
	const variableName = ...
	const function() ...
	const functionName() ...
	```

Use PascalCase for Classes and Constructors

	```javascript
	// good
	const MyClass = ...
	```

<a name='formatting--spelling'></a><a name='1.10'></a>
- [1.10](#formatting-spelling) **Spelling Counts**
Please check your spelling. Typos hurt my brain.

	```javascript
	// bad
	Smrt

	// good
	Smart
	```

## Comments

<a name='comments--single'></a><a name="2.1"></a>
- [2.1](#comments--single) **Use `//` for single line comments**

	```javascript
	// Single line comment
	```

<a name='comments--indent'></a><a name="2.2"></a>
- [2.2](#comments--indent) **Indent single line comments with their respective lines of code**

	```javascript
	// bad
		// Comment
	const a = 1;

	// bad
	const a = 1; // Comment

	// good
	// Comment
	const a = 1;
	```

<a name='comments--space'></a><a name="2.3"></a>
- [2.3](#comments--space) **Begin all single line comments with a space**

	```javascript
	// bad
	//Comment
	const a = 1;

	// good
	// Comment
	const a = 1;
	```

<a name='comments--multiple'></a><a name="2.4"></a>
- [2.4](#comments--multiple) **Use `/&ast;&ast; ... &ast;/` for multiple line comments**

	```javascript
	/&ast;&ast; Multiple
	  &ast; lines
	  &ast; of
	  &ast; comments
	  &ast;/
	```

## Variables

<a name='variables--declaration'></a><a name='3.1'></a>
- [3.1](#variables-declaration) **Declaration**
Avoid declaring global variables when unnecessary.
Use const or let to declare variables.
Don't use var to avoid reassigning references.

	```javascript
	// bad
	var a = 1;

	// good
	const a = 1;

Use let if reassigning references.

	```javascript
	// bad
	var count = 0;
	if (true) {
		count += 1;
	}

	// good
	let count = 0;
	if (true) {
		count += 1;
	}

Group variable types together.

	// bad
	const a = 1;
	let count = 0;
	const b = 2;

	// good
	const a = 1;
	const b = 2;

	let count = 0;
	```

Declare variables on a new line.

	```javascript
	// bad 
	const a = 1, b = 2;

	// good
	const a = 1;
	const b = 2;
	```

## Objects

<a name="objects--no-new"></a><a name="4.1"></a>
- [4.1](#objects--no-new) Use the literal syntax for object creation.

    ```javascript
    // bad
    const item = new Object();

    // good
    const item = {};
    ```

## Arrays

<a name="arrays--literals"></a><a name="5.1"></a>
- [5.1](#arrays--literals) Use the literal syntax for array creation.

    ```javascript
    // bad
    const items = new Array();

    // good
    const items = [];
    ```

<a name="arrays--push"></a><a name="5.2"></a>
- [5.2](#arrays--push) Use Array push instead of direct assignment to add items to an array.

    ```javascript
    const someStack = [];

    // bad
    someStack[someStack.length] = 'abracadabra';

    // good
    someStack.push('abracadabra');
    ```

## Conditionals and Loops

<a name='conditionals--operators'></a><a name='6.1'></a>
- [6.1](#conditionals--operators) **Use `===` insead of `==` and `!==` instead of `!=`**

<a name="conditionals--shortcuts"></a><a name="6.2"></a>
  - [6.2](#conditionals--shortcuts) Use shortcuts for booleans, but explicit comparisons for strings and numbers.

    ```javascript
    // bad
    if (isValid === true) {
      // ...
    }

    // good
    if (isValid) {
      // ...
    }

    // bad
    if (name) {
      // ...
    }

    // good
    if (name !== '') {
      // ...
    }

    // bad
    if (collection.length) {
      // ...
    }

    // good
    if (collection.length > 0) {
      // ...
    }
    ```

<a name="conditionals--switch-blocks"></a><a name="6.3"></a>
  - [6.3](#conditionals--switch-blocks) Use braces to create blocks in `case` and `default` clauses that contain lexical declarations (e.g. `let`, `const`, `function`, and `class`).

    ```javascript
    // bad
    switch (foo) {
      case 1:
        let x = 1;
        break;
      case 2:
        const y = 2;
        break;
      case 3:
        function f() {
          // ...
        }
        break;
      default:
        class C {}
    }

    // good
    switch (foo) {
      case 1: {
        let x = 1;
        break;
      }
      case 2: {
        const y = 2;
        break;
      }
      case 3: {
        function f() {
          // ...
        }
        break;
      }
      case 4:
        bar();
        break;
      default: {
        class C {}
      }
    }
    ```

## Events

<a name="events--hash"></a><a name="7.1"></a>
- [7.1](#events--hash) When attaching data payloads to events (whether DOM events or something more proprietary like Backbone events), pass a hash instead of a raw value. This allows a subsequent contributor to add more data to the event payload without finding and updating every handler for the event.

    ```javascript
    // bad
    $(this).trigger('listingUpdated', listing.id);

    // ...

    $(this).on('listingUpdated', (e, listingId) => {
      // do something with listingId
    });
    ```

prefer:

    ```javascript
    // good
    $(this).trigger('listingUpdated', { listingId: listing.id });

    // ...

    $(this).on('listingUpdated', (e, data) => {
      // do something with data.listingId
    });
    ```

## jQuery

<a name="jquery--dollar-prefix"></a><a name="8.1"></a>
- [8.1](#jquery--dollar-prefix) Prefix jQuery object variables with a `$`.

    ```javascript
    // bad
    const sidebar = $('.sidebar');

    // good
    const $sidebar = $('.sidebar');

    // good
    const $sidebarBtn = $('.sidebar-btn');
    ```

<a name="jquery--cache"></a><a name="8.2"></a>
- [8.2](#jquery--cache) Cache jQuery lookups.

    ```javascript
    // bad
    function setSidebar() {
      $('.sidebar').hide();

      // ...

      $('.sidebar').css({
        'background-color': 'pink',
      });
    }

    // good
    function setSidebar() {
      const $sidebar = $('.sidebar');
      $sidebar.hide();

      // ...

      $sidebar.css({
        'background-color': 'pink',
      });
    }
    ```

## Resources

<a name="resources--other-styles"></a><a name="9.1"></a>
- [9.1](#resources--other-styles) **Style Guides**

  - [JSCS Rules](http://jscs.info/rules)
  - [jQuery Foundation JavaScript Style Guide](https://contribute.jquery.org/style-guide/js/)

<a name="resources--jshint"></a><a name="9.2"></a>
- [9.2](#resources--other-styles) **JSHint**

  - [JSHint online checker](http://jshint.com/)