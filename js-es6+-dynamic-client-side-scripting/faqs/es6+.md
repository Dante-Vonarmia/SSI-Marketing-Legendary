# ES6+ new features

## What kinds of declaration does ES6 introduced? What are the scopes of each of them?

## What is an arrow function? 

First, it’s a new feature in ES6 standard. One thing worth to be mentioned is an arrow function actually doesn’t include the constructor. So, the context will be its outer.

## Difference between regular functions and arrow functions in JavaScript

#### **Arrow function has no keywords: `this`, argument**

So an arrow function as actionHandler no need to do `bind` in constructor

An arrow function expression is a syntactically compact alternative to a regular function expression, although without its own bindings to the `this`, arguments, `super`, or new.target keywords. Arrow function expressions are illustrated as methods, and they cannot be used as constructors.

* Arrow functions do not have a prototype property.
* Arrow functions cannot be used as constructors and will throw an error when used with `new`

Since arrow functions do not have their own this, the methods `call()` and `apply()` can only pass in parameters. Any this argument is ignored.

