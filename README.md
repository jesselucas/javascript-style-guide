javascript-style-guide
======================

##Linting

Use JSHint for formatting, and make sure to follow it's advice. You should set JSHint options in a ```.jshintrc``` file. Read the JSHint docs for more information: http://www.jshint.com/docs/

##Spacing

* Indent with tabs
//example
* Always use braces for if/else/for/while/try with  line breaks and whitespace.

```
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

```
	// Bad
	var item = new Object();
	
	// Good
	var item = {};
```
