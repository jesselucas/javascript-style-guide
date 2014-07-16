JavaScript Style Guide
======================
##General

> "All code in any code-base should look like a single person typed it, no matter how many people contributed." - [idiomatic.js](https://github.com/rwaldron/idiomatic.js/#all-code-in-any-code-base-should-look-like-a-single-person-typed-it-no-matter-how-many-people-contributed)

> "Arguments over style are pointless. There should be a style guide, and you should follow it" - Rebecca Murphey

##Linting

Use JSHint for formatting, and make sure to follow it's advice. You should set JSHint options in a ```.jshintrc``` file. Read the JSHint docs for more information: http://www.jshint.com/docs/

##Spacing

In general we prefer the formating of JsFormat - https://github.com/jdc0589/JsFormat

- Always use braces for if/else/for/while/try with  line breaks and whitespace before and after parens.

```javascript
// Bad
if(condition) doSomething();

for(var i=0;i<10;i++) someFunction();

// Good 
if (condition) {
    doSomething();
}


for (var i = 0; i < 10; i++) {
    SomeFunction();
}
```

## Variables and Assignments

- Always use the ```var``` keyword to declare variables otherwise it will be declared in the global namespace.

```
// Bad
foo = false;

// Good
var foo = false;
```

- Only use ```var``` one time when declaring multiple variables

```
// Bad
var foo = false;
var bar = true;
var person = "";
var i = 0;

// Good
var foo = false,
    bar = true,
    person = "",
    i = 0;

```

- Declare unassigned variables last and on their own line.

```
// Bad
var person, i, 
    foo = false;
    bar = true;

// Good
var foo = false;
    bar = true
    person,
    i;
```

##Objects

- Use literal notation when declaring objects

```javascript
// Bad
var item = new Object();

// Good
var item = {};
```

##Arrays

- Use literal notation when declaring arrays

```javascript
// Bad
var list = new Array();

// Good
var list = [];
```

##Conditionals and Equality

- Always use identity comparison operators (```===```) and (```!==```). The (```==```) and (```!=```) operators do type coercion and should not be used. 

```javascript
// Bad
if (foo == 1) {
    doSomething();
} else if (foo != 1) {
    doSomethingIfElse();
} else {
    doSomethingElse();
}

// Good
if (foo === 1) {
    doSomething();
} else if (foo !== 1) {
    doSomethingIfElse();
} else {
    doSomethingElse();
}
```
- The only exception is when checking undefined or null against null

```javascript
// Check for both undefined and null values, for some important reason.
undefinedOrNull == null;
```

##Functions

- Declare your variables at the beginning of the function 

```
// Bad
function bad() {
    // some statements

    var item = {};
}

// Good
function good() {
    var item = {};

    // some statement
}
```

- Don't declare a function in a non-function block

```
// Bad
if (item) {
    function bad() {
        // don't do this
    }
}

// Good
var good;
if (item) {
    good = function good() {
        // do this
    };
}
```

##Naming

- Make variabls and function names full words and try to be descriptive using camelCase

```
// Bad
function check(w) {
    return w;
}

var i, wArray=new Array();
for(i=0;i<wArray.length;i++){check(wArray[i])};

// Good
function checkForWord(word) {
    return word;
}

var i = 0,
    words = [],
    length = words.length,
    match;

for ( ; i < length; i++) {
    match = checkForWord(words[i]);
}

```

##Quotes

##Type Checking

##Comments


##Sources and Other Useful Guides
* [Google](https://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml)
* [idiomatic.js](https://github.com/rwaldron/idiomatic.js/)
* [jQuery](http://contribute.jquery.org/style-guide/js/)
* [Airbnb](https://github.com/airbnb/javascript)
* [Douglas Crockford](http://javascript.crockford.com/code.html)
