# Core Mechanism

## How context is different from the scope?

The scope is the accessibility of variables, functions, or objects in some particular part of your code during runtime.

Context is always the value of the `this` keyword which is a reference to the object that “owns” the currently executing code.

## How does the context behave in an execution context?

The value of `this` is determined at creation phase, not at the time of execution.  However, `this` determination rule remains the same.Is JavaScript an Interpreted or a compiled language?

Yes, Javascript \(JS\) is an interpreted language,  
still has its own form of a compiler, run in what’s known as the Javascript engine\(Chrome V8\).

JavaScript has a concurrency model based on an event loop,  
which is responsible for executing the code, collecting and processing events, and executing queued sub-tasks.  
This model is quite different from models in other languages like C and Java.Can you name two programming paradigms that are important for JavaScript developers?

* Prototypal inheritance \(also: prototypes, OLOO -- Object Linking to Other Objects\).
* Functional programming \(also: closures, first class functions, lambdas\).

## What does “favor object composition over class inheritance” mean?

* use can-do, has-a, or uses-a relationships instead of is-a relationships.
* Avoid class hierarchies.
* Avoid brittle base class problem.
* Avoid tight coupling.
* Avoid rigid taxonomy \(forced is-a relationships that are eventually wrong for new use cases\).
* Avoid the gorilla banana problem \(“what you wanted was a banana, what you got was a gorilla holding the banana, and the entire jungle”\).
* Make code more flexible.

## What are the pros and cons of functional programming vs object-oriented programming?

## Explain what is the operation mechanism of the JavaScript. \(hint: event-loop, call-stack\)

## List some OOP concept that is actually adopted in JavaScript.

* Objects
* Encapsulation
* Inheritance
* Instance

