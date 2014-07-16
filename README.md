JavaScript Style Guide
======================
##General

"All code in any code-base should look like a single person typed it, no matter how many people contributed." - [idiomatic.js](https://github.com/rwaldron/idiomatic.js/#all-code-in-any-code-base-should-look-like-a-single-person-typed-it-no-matter-how-many-people-contributed)

##Linting

Use JSHint for formatting, and make sure to follow it's advice. You should set JSHint options in a ```.jshintrc``` file. Read the JSHint docs for more information: http://www.jshint.com/docs/

##Spacing

In general we prefer the formating of JsFormat - https://github.com/jdc0589/JsFormat

* Always use braces for if/else/for/while/try with  line breaks and whitespace before and after parens.

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

##Objects

* Use literal notation when declaring objects

```javascript
// Bad
var item = new Object();

// Good
var item = {};
```

##Arrays

* Use literal notation when declaring arrays

```javascript
// Bad
var list = new Array();

// Good
var list = [];
```

##Conditionals

* Use identity comparison operators

```javascript
// Bad
if (foo == 1) {
    doSomething();
} else if (foo != 1) {
    doSomethingElse();
} else {
    //code
}

// Good
if (foo === 1) {
    doSomething();
} else if (foo !== 1) {
    doSomethingElse();
} else {
    //code
}
```

##Sources and Other Useful Guides
* [Google](https://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml)
* [idiomatic.js](https://github.com/rwaldron/idiomatic.js/)
* [jQuery](http://contribute.jquery.org/style-guide/js/)
* [Airbnb](https://github.com/airbnb/javascript)
* [Douglas Crockford](http://javascript.crockford.com/code.html)
