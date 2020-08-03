# Misc

## Given a id string, sum it up till only one digit. 

For instance, 55555 - 25 - 7, return 7

```javascript
let n = 55555; // Any positive integer
function onlyOneDigit(n) {
	if (n === 0)
		return 0
	else
		return n % 9 || 9
}

console.log(onlyOneDigit(n)) // Output: 7
```

