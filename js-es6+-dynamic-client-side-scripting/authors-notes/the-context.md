# THE Context

## Is JavaScript an Interpreted or a compiled language?

Yes, Javascript \(JS\) is an interpreted language,  
still has its own form of a compiler, run in what’s known as the Javascript engine\(Chrome V8\).

JavaScript has a concurrency model based on an event loop,  
which is responsible for executing the code, collecting and processing events, and executing queued sub-tasks.  
This model is quite different from models in other languages like C and Java.

## Execution Context

1. Global Execution Context
   * Create a ‘window’ object.
   * The window object is referenced to ‘this’ keyword.
2. Function Execution Context
   * Whenever the code execution found a function it creates a new function execution contexts. 

## Execution Stack / Call Stack

> Execution Context Phases

In short, execution context is the ‘environment’ or scope in which a function executes in.  
Every time a function is called, a new execution context is created.  
Every call to an execution context has 2 stages

* Creation Phase
  * A connection to the outer environment is created
  * Global environment: the outer environment is null
  * All functions and variables: form a scope chain all done in a memory of a web browser
  * Determined `this` keyword
* Activation\(Execution\) Phase
  * When the function is executed
  * Executed function will be popped off the stack and move onto the next one
  * `var` defined variables can be accessed before they are declared \(though undefined\) 
  * Variable hoisted / lifted: leaking `this`

## How context is different from the scope?

The scope is the accessibility of variables, functions, or objects in some particular part of your code during runtime.

Context is always the value of the `this` keyword which is a reference to the object that “owns” the currently executing code.

## How does the context behave in an execution context?

The value of `this` is determined at creation phase, not at the time of execution.  However, `this` determination rule remains the same.

