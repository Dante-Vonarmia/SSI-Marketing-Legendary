# ES6+ Basic Concept

```javascript
/////////////////////////
// var vs let vs const //
/////////////////////////

	// ES6+ has a total of 6 ways to declare variables.

	// ES5 has only two ways to declare variables: 
	// 	the var command and the function command.

	// ES6 has added four more declare variables:
	// 	the let and const commands
	// 	the import command
		// module
		// import
			import moduleName from 'module'
			import { originalName as alias } from 'module'
		// export
			export default moduleName
	// 	the class command
		// Explain in React Lecture

////////////////////
// Deconstructing //
////////////////////

	// In essence, this writing belongs to "pattern matching". 
	// As long as the pattern on both sides of the equal sign is the same,
	// the variable on the left will be assigned a corresponding value. 

		// Usage:
			// 1. switch value;
				let x = 1;
				let y = 2;

				[x, y] = [y, x];

			// 2. Return multiple values
				// return an array

				function example() {
					return [1, 2, 3];
				}
				let [a, b, c] = example();

				// return an object
				function example() {
					return {
						foo: 1,
						bar: 2
					};
				}
				let {
					foo,
					bar
				} = example();

			// 3. Extract JSON data
				let jsonData = {
					id     : 42,
					status : "OK",
					data   : [867, 5309]
				};

				let { id, status, data: number } = jsonData;
				console.log(id, status, number); // 42, "OK", [867, 5309]

			// 4. Iterate `Map` structure
				const map = new Map();
				map.set('first', 'hello');
				map.set('second', 'world');

				for (let [key, value] of map) {
					console.log(key + " is " + value);
				}

///////////////////
// Rest + Spread //
///////////////////

	// Basic Syntax
	console.log(...[1, 2, 3])
	// 1 2 3

	console.log(1, ...[2, 3, 4], 5)
	// 1 2 3 4 5
	
	console.log(1, ...[2, 3, 4], 5, ...)
	// error
	
	// e.q. 1
	// ES5:
	Math.max.apply(null, [14, 3, 77])
	// ES6:
	Math.max(...[14, 3, 77])
	// same to
	Math.max(14, 3, 77);

	// e.q. 2
	// ES5:
	var arr1 = [0, 1, 2];
	var arr2 = [3, 4, 5];
	Array.prototype.push.apply(arr1, arr2);
	// ES6:
	let arr1 = [0, 1, 2];
	let arr2 = [3, 4, 5];
	arr1.push(...arr2);
			
/////////////////////////////
// Function Syntactic Sugar //
/////////////////////////////

	// default parameter value
	function log({x, y = 'World'}) {
		console.log(x, y);
	}

	log({x: 'hello'})

	// Rest parameters
	function _push(...values) {
		let arr = [...values];
		return arr;
	}

	_push(2, 5, 3) // [2, 5, 3]

	// Arrow function
		// e.q.
		var a = b => b
		// same as
		var a = function (b) {
			return b;
		}
		
		var array = [2, 4, 5, 22, 1, 8,10, 6, 44, 7, 3, 9, 11, 33];
		const arr = [...array].map(temp => parseInt(temp, 10)).sort((a, b) => a - b);
			// sort() vs sort((a, b) => a - b)
			// immutable
		console.log(arr);

		// Sort array in element's length.
		function mode(arr) {
			return arr.sort((a, b) =>
				arr.filter(v => v === a).length - arr.filter(v => v === b).length
			);
		}

//////////////////////////////////////////////////
// Math + Number + String + Object + Array APIs //
//////////////////////////////////////////////////

	Number.EPSILON // check object is finite or not.
	Number.isInteger(Infinity) // false
	Number.isNaN("NaN") // false

	Math.acosh(3) // 1.762747174039086
	Math.hypot(3, 4) // 5
	Math.imul(Math.pow(2, 32) - 1, Math.pow(2, 32) - 2) // 2

	"abcde".includes("cd") // true
	"abc".repeat(3) // "abcabcabc"

	Object.assign(Point, { origin: new Point(0,0) })

	Array.from(document.querySelectorAll('*')) // Returns a real Array
	Array.of(1, 2, 3) // Similar to new Array(...), but without special one-arg behavior
	[0, 0, 0].fill(7, 1) // [0,7,7]
	[1, 2, 3].find(x => x == 3) // 3
	[1, 2, 3].findIndex(x => x == 2) // 1
	[1, 2, 3, 4, 5].copyWithin(3, 0) // [1, 2, 3, 1, 2]
	["a", "b", "c"].entries() // iterator [0, "a"], [1,"b"], [2,"c"]
	["a", "b", "c"].keys() // iterator 0, 1, 2
	["a", "b", "c"].values() // iterator "a", "b", "c"

/////////////////////////
// iterators: `for of` //
/////////////////////////
	
	// e.q.
	function makeIterator(array) {
		let nextIndex = 0;
		return {
			next: function() {
				return nextIndex < array.length ? {
					value: array[nextIndex++],
					done: false
				} : {
					value: undefined,
					done: true
				};
			}
		};
	}
	
	let it = makeIterator(['a', 'b']);

	it.next() // { value: "a", done: false }
	it.next() // { value: "b", done: false }
	it.next() // { value: undefined, done: true }

	// The data structure of the Iterator interface is as follows
	// 	Array
	// 	String
	// 	Map
	// 	Set
	// 	TypedArray
	// 	Function's arguments object
	// 	NodeList object

	// basic theory of an iterators

	const obj = {
		[Symbol.iterator]: function() {
			return {
				next: function() {
					return {
						value: null,
						done: true
					};
				}
			};
		}
	};

	// e.q.
	let arr = ['a', 'b', 'c'];
	let iter = arr[Symbol.iterator]();

	iter.next() // { value: 'a', done: false }
	iter.next() // { value: 'b', done: false }
	iter.next() // { value: 'c', done: false }
	iter.next() // { value: undefined, done: true}


	//  *Symbol
		// A new primitive type
		// A mechanism to ensure that the name of each attribute is unique, 
		// so that the conflict of attribute names is fundamentally prevented.

		let s1 = Symbol();
		let s2 = Symbol();

		s1 === s2 // false

		let s1 = Symbol.for();
		let s2 = Symbol.for();

		s1 === s2 // true

		let t1 = Symbol.for("foo");
		Symbol.keyFor(t1) // "foo"

		let t2 = Symbol("foo");
		Symbol.keyFor(t2) // undefined

	// Set and Map
		// e.q. Set
			// Object member's values are unique
			// Set. It is a constructor itself, used to generate "Set" data structure
				// Set.prototype.constructor
			// The Set function can accept an array (or other data structure with an iterable interface) as a parameter for initialization.
			var arr = [1, 2, 3, 1, 2]; 
			var newArr= [...new Set(arr)];

			// Merge the following two array and The output should be
			// [
			//   { id: 1, name: "David", position: null },
			//   { id: 2, name: "John", position: "Leader" },
			//   { id: 3, name: "Matt", position: "Captain" },
			//   { id: 4, name: "Greg", position: "VP" },
			//   { id: 5, name: null, position: "Pawn" },
			//   { id: 6, name: null, position: "Rogue" }
			// ];

		// e.q. Map
			// JavaScript objects are essentially collections of key-value pairs (Hash structures),
			// But traditionally only strings can be used as keys. This puts a lot of restrictions on its use.
			// 'key' : value
			// 'key' ==> data[element] = 'metadata';

		// e.q. Map 1
			const m = new Map();
			const o = {
				p: 'Hello World'
			};

			m.set(o, 'content')
			m.get(o) // "content"

			// e.q. Map 2
			const a = [{id: 3,name: "Matt"}, {id: 4,name: "Greg"}, {id: 1,name: "David"}, {id: 2,name: "John"}];
			const b = [{id: 2,position: "Leader"}, {id: 3,position: "Captain"}, {id: 6,position: "Rogue"}, {id: 4,position: "VP"}, {id: 5,position: "Pawn"}];

			const _hash = new Map();
			const c = [...a, ...b];
			c.map(obj => {
				_hash.set(obj.id, {
					position: null,
					name: null,
					..._hash.get(obj.id),
					...obj
				});
			});
			const result = Array.from(_hash.values()); // Iteration operation value keys entries ...


/////////////
// Promise //
/////////////

	// see promise/basic.js

///////////////
// Generator //
///////////////

	// 语法上, Generator 函数是一个状态机，封装了多个内部状态
	// 	执行 Generator 函数会返回一个遍历器对象
	// 形式上，Generator 函数是一个普通函数，但是有两个特征。
	// 	一是，function关键字与函数名之间有一个星号；
	// 	二是，函数体内部使用yield表达式，定义不同的内部状态（yield在英语里的意思就是“产出”）。

	// Syntactically, the Generator function is a state machine that encapsulates multiple internal states
	// 	Executing the Generator function returns a Iteration object
	// Formally, the Generator function is a normal function, but has two characteristics.
		
		// Pausable Function
		function* f() {
			yield console.log("I'm a generator function."); 
			yield console.log("The Generator function is a state machine.");
			yield console.log("Executing the Generator function returns a Iteration object.");
			yield console.log("The Generator function is a normal function, but has two characteristics.");
			// return undefined;
		}

		const run_f = f();
		run_f.next();
		// First, there is an asterisk between the function keyword and the function name;
		// Second, the yield expression is used inside the function body to define different internal states (yield means "output" in English).

	// Used as create an iterator

```

