# \`this\` keyword Binding Methods

## Context — Implicit Binding

Called as a method of an object.

#### Sample 1

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

#### Sample 2

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

