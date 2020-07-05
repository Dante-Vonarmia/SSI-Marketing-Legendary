# Variables

## `null` vs `Undefined`

### Null

* `null` variable is assigned.
* `null` variable is always intentional.
* `null` variable indicates a lack of value.

### Undefined

* `undefined` variable can be assigned.
* `undefined` variable is often unintentional.
* `undefined` variable indicates a variable is declared but not defined.

### Both

* Both `null` and `undefined` are primitives values.
* Both `null` and `undefined` are falsy values.
* `null` and `undefined` are loosely equal.

## Common comparison

### The Equality Operator

```javascript
""           ==   "0"           // F
0            ==   ""            // T
0            ==   "0"           // T
false        ==   "false"       // F
false        ==   "0"           // T
false        ==   undefined     // F
false        ==   null          // F
null         ==   undefined     // T
" \t\r\n"    ==   0             // T
```

### The Strict Equality Operator

```javascript
""           ===   "0"           // F
0            ===   ""            // F
0            ===   "0"           // F
false        ===   "false"       // F
false        ===   "0"           // F
false        ===   undefined     // F
false        ===   null          // F
null         ===   undefined     // F
" \t\r\n"    ===   0             // F
```

### Comparing Objects

```javascript
new String('foo') === 'foo';     // F
new Number(10) === 10;           // F
let foo = {};
foo === foo;                     // T
{} === {}                        // Error
```

