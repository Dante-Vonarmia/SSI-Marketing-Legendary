# React Syntax

## What is Imperative Implementation and Declarative Programming mean?

### Imperative Implementation

It is basically telling the computer **how** to do something, and as a result what you want to happen will happen.

### Declarative Programming

In declarative programming, the program tells the computer **what** you would like to happen, and lets the computer figure out how to do it.

### Perspective in React

The React component never actually touches an element. it simply declares an element _should_ be rendered given our current state. It does not actually manipulate the DOM itself.

When writing React, it’s often good not to think of _how_ you want to accomplish a result, but instead _what_ the component should look like in its new state.This sets us up for a good control flow where state goes through a series of predictable and replicable mutations. This doesn’t just apply to components either, but also to application state. Libraries like [Redux](http://redux.js.org/) will help enforce this method of architecting, but they aren’t necessary to achieve it.

## How React works? How Virtual-DOM works in React?

### React work principles

React creates a virtual DOM. When state changes in a component it firstly runs a “diffing” algorithm, which identifies what has changed in the virtual DOM. The second step is reconciliation, where it updates the DOM with the results of diff.

The HTML DOM is always tree-structured — which is allowed by the structure of HTML document. The DOM trees are huge nowadays because of large apps. Since we are more and more pushed towards dynamic web apps \(Single Page Applications — SPAs\), we need to modify the DOM tree incessantly and a lot. And this is a real performance and development pain.

### Virtual-DOM work principles

The Virtual DOM is an abstraction of the HTML DOM. It is lightweight and detached from the browser-specific implementation details. It is not invented by React but it uses it and provides it for free. `ReactElements` lives in the virtual DOM. They make the basic nodes here. Once we defined the elements, `ReactElements` can be render into the "real" DOM.

Whenever a `ReactComponent` is changing the state, diff algorithm in React runs and identifies what has changed. And then it updates the DOM with the results of diff. The point is - it’s done faster than it would be in the regular DOM.

## Explain what is the difference between the Real DOM and virtual **DOM**?

React uses Virtual DOM to update the real DOM which makes it efficient and faster**.**

\*\*\*\*

## How Virtual-DOM is more efficient than Dirty checking?

In React, each of our components have a state. This state is like an observable. Essentially, React knows when to re-render the scene because it is able to observe when this data changes. Dirty checking is slower than observables because we must poll the data at a regular interval and check all of the values in the data structure recursively. By comparison, setting a value on the state will signal to a listener that some state has changed, so React can simply listen for change events on the state and queue up re-rendering.

The virtual DOM is used for efficient re-rendering of the DOM. This isn’t really related to dirty checking your data. We could re-render using a virtual DOM with or without dirty checking. In fact, the diff algorithm is a dirty checker itself.

We aim to re-render the virtual tree only when the state changes. So using an observable to check if the state has changed is an efficient way to prevent unnecessary re-renders, which would cause lots of unnecessary tree diffs. If nothing has changed, we do nothing.

## What is JSX? Can browser recognize the JSX? Why?

### **Definition**

**JSX is a syntax extension to JavaScript and comes with the full power of JavaScript.** 

JSX produces React “elements”. You can embed any JavaScript expression in JSX by wrapping it in curly braces. After compilation, JSX expressions become regular JavaScript objects. This means that you can use JSX inside of if statements and for loops, assign it to variables, accept it as arguments, and return it from functions. Even though React does not require JSX, it is the recommended way of describing our UI in React app.

### JSX with Browser

JSX is not valid JavaScript, web browsers cant read it directly. So, if JavaScript files contains JSX, that that file will have to be transpiled. That means that before the file gets to the web browser, a JSX compiler will translate any JSX into regular JavaScript.

JSX produces React “elements”. A React element is simply an object representation of a DOM node. A React element isn’t actually the thing we see on our screen, instead, it’s just an object representation of it. We can embed any JavaScript expression in JSX by wrapping it in curly braces.  


## What is the difference between state and props?

## What is the context in React?

## What is the lifting state up?

## How to Update State and How to avoid the wrong way?

## Is setState\(\) is async? If yes, why is setState\(\) in React Async instead of Sync?

## What is the second argument that can optionally be passed to setState and what is its purpose?

## If I want to pass some certain data into the event handler, how would you do?

## What is the HOC? Why do we need this in the react?

## Why do we need a key in the react?

## What data flow does React follow?

## Composition Over Inheritance, why?

## What are Error Boundaries?

## What are Fragments?

## What are prop-types and what are the benefits and drawbacks of them?

