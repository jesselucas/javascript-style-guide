JavaScript Style Guide
======================
## Table of Contents

 * [General](#general)
 * [Linting](#linting)
 * [Spacing](#spacing)
 * [Variables and Assignments](#variables-and-assignments)
 * [Objects](#objects)
 * [Arrays](#arrays)
 * [Conditionals and Equality](#conditionals-and-equality)
 * [Functions](#functions)
 * [Naming](#naming)
 * [Quotes](#quotes)
 * [Type Checking](#type-checking)
 * [Comments](#comments)
 * [Sources and Other Useful Guides](#sources-and-other-useful-guides)


## General

> "All code in any code-base should look like a single person typed it, no matter how many people contributed." - [idiomatic.js](https://github.com/rwaldron/idiomatic.js/#all-code-in-any-code-base-should-look-like-a-single-person-typed-it-no-matter-how-many-people-contributed)

> "Arguments over style are pointless. There should be a style guide, and you should follow it" - Rebecca Murphey

## Linting

- Use JSHint for formatting, and make sure to follow it's advice. You should set JSHint options in a ```.jshintrc``` file. Read the JSHint docs for more information: http://www.jshint.com/docs/

- Please reference the provided ```.jshintrc``` file for our preferred options

## Spacing

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

    ```javascript
    // Bad
    foo = false;

    // Good
    var foo = false;
    ```

- Only use ```var``` one time when declaring multiple variables

    ```javascript
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

    ```javascript
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

## Objects

- Use literal notation when declaring objects

    ```javascript
    // Bad
    var item = new Object();

    // Good
    var item = {};
    ```

## Arrays

- Use literal notation when declaring arrays

    ```javascript
    // Bad
    var list = new Array();

    // Good
    var list = [];
    ```

## Conditionals and Equality

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

## Functions

- Declare your variables at the beginning of the function 

    ```javascript
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

    ```javascript
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

## Naming

- Make variables and function names full words and try to be descriptive using camelCase

    ```javascript
    // Bad
    function check(w) {
        // check wArray and return word
        return w;
    }

    var i, mArray=new Array();
    for(i=0;i<wArray.length;i++){mArray.push(check())};

    // Good
    function checkForWord(word) {
        // Check words array and return word
        return word;
    }

    var i = 0,
        matches = [],
        length = words.length,
        match;

    for ( ; i < length; i++) {
        match = checkForWord(words[i]);
    }

    ```

- When storing a reference to ```this``` use ```_this``` 

    ```javascript
    // Bad
    function() {
        var self = this;
        return function() {
            console.log(self);
        };
    }

    // Good
    function() {
        var _this = this;
        return function() {
            console.log(_this);
        };
    }
    ```

## Quotes

- Use double quotes

    ```javascript
    var fullName = "Muhammad Ali";
    ```

- Use single quotes inside strings

    ```javascript
    var span = "<span class='.firstName'></span>";
    ```


## Type Checking - [jQuery Core Style Guidelines](http://contribute.jquery.org/style-guide/js/)

- String:

    ```javascript 
    typeof object === "string"
    ```
    
- Number: 

    ```javascript 
    typeof object === "number"
    ```

- Boolean:

    ```javascript 
    typeof object === "boolean"
    ```

- Object:

    ```javascript 
    typeof object === "object"
    ```

- Plain Object:

    ```javascript 
    jQuery.isPlainObject(object)
    ```

- Function

    ```javascript 
    jQuery.isFunction( object )
    ```
    
- Array: 
    ```javascript 
    jQuery.isArray( object )
    ```

- Element: 
    
    ```javascript 
    object.nodeType
    ```

- null: 
    ```javascript 
    object === null
    ```

- null or undefined: 
    ```javascript 
    object == null
    ```

- undefined:
    - Global Variables: 
        ```javascript 
        typeof variable === "undefined" 
        ```
    - Local Variables: 
        ```javascript 
        variable === undefined
        ```
    - Properties: 
        ```javascript 
        object.prop === undefined
        ```

## Comments

- Single line comments should have a space after the ```//``` and be on it's own line.

    ```javascript
    // Bad
    var activeItems = []; //we'll use this array to store all active items

    // Good
    // We'll use this array to store all active items
    var activeItems = [];
    ```

- Make sure there is an empty line above your comments
    
    ```javascript
    // Bad
    function setActiveItem() {
        console.log("Setting the active item");
        // Create a new item and add it to activeItems
        var newItem = {};
        activeItems.push(newItem);
    }

    // Good
    function setActiveItem() {
        console.log("Setting the active item");

        // Create a new item and add it to activeItems
        var newItem = {};
        activeItems.push(newItem);
    }
    ```

## Sources and Other Useful Guides
* [Google](https://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml)
* [idiomatic.js](https://github.com/rwaldron/idiomatic.js/)
* [jQuery](http://contribute.jquery.org/style-guide/js/)
* [Airbnb](https://github.com/airbnb/javascript)
* [Douglas Crockford](http://javascript.crockford.com/code.html)
