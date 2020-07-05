# "this" keyword Binding Methods

## Context — Implicit Binding

Called as a method of an object.

#### Basic Example 1

```javascript
function func() {
	return this;
}

func() // window object

var obj = {
	method: func
};

obj.method() === obj // true
obj.method() === window // false
```

#### Basic Example 2

```javascript
var obj = {
	a: 1,
	getA: function() {
		console.log(this === obj); // Output: true 
		console.log(this.a); // Output: 1
	}
};
obj.getA();
```

## New Binding

Whereas if we do new `foo()` at the global level then will get this as `foo {}` object.

#### Basic Example

```javascript
// Constructor call
function foo() {
	console.log(this);
}

foo() // window object

new foo() // foo {}
```

### Introduce `new`

#### `new`: 

* Creates a blank, plain JavaScript object; 
* Links \(sets the constructor of\) this object to another object; 
* Passes the newly created object from Step 1 as the this context; 
* Returns this if the function doesn't return its own object.

#### constructor:

* A class or function that specifies the type of the object instance. 
* A constructor enables you to provide any custom initialization that must be done before any other methods can be called on an instantiated object.

#### arguments :

* A list of values that the constructor will be called with.

### Begin Prototype

#### Basic Example:

```javascript
var MyClass = function() {
	console.log(this)
	this.name = 'dva89';
	return { // Return an object explicitly
		name: 'anne'
	}
	// return 'anne' // return a string
};

var _obj = new MyClass(); // (factory pattern)
```

### Proto method 1: `Object.prototype.constructor`

* The `constructor` property returns a reference to the `Object` constructor function that created the instance object.
* Note that the value of this property is a reference to the function itself, not a string containing the function's name.
* The value is only read-only for primitive values.

```javascript
var MyClass = function() { // MyClass {}
	this.name = 'dva89';
};

MyClass.prototype.age = function(a) { // MyClass { name: 'dva89' }
	return a;
};

var _obj = new MyClass(); // (factory pattern)

Object.prototype.toString.call(_obj) // [object object]

_obj.name; // dva89
_obj.age(30); // 30
typeof new MyClass(); // object
new MyClass().age(30); // 30
```

#### `proto` vs prototype

```javascript
// (continue previous example)
_obj // MyClass { name: 'dva89' }
_obj.__proto__ // // MyClass { age: [λ] }
```

### Proto Method 2:  `object`

```javascript
var MyClass2 = {
	name: function() {
		return this.name = 'dva89'
	}
};

MyClass2.age = function(a) {
	return a
};

MyClass2 // ​​​​​{ name: [λ: name], age: [λ] }​​​​​
MyClass2.__proto__ // {}
```

### Proto method 3: `Object.setPrototypeOf()`

```javascript
var country = {
	region: 'China'
}

Object.setPrototypeOf(MyClass2, country)
MyClass2.region // China


var _obj2 = Object.create(MyClass2)
 
_obj2.name() // dva89
_obj2.age(30) // 30
_obj2.region // China

_obj2 // { name: 'dva89' }
_obj2.__proto__ // ​​​​​{ name: [λ: name], age: [λ] }​​​​​
_obj2.__proto__.__proto__ // { region: 'China' }
```

#### `Object.create()` vs `new`

This is due to the important difference that `new` actually runs constructor code, whereas `Object.create` will not execute the constructor code.

