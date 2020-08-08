# Mathematic Approaches

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

## A Fibonacci number \(Memoization\)

```javascript
const fib = (num) => {
  let a = 1,
    b = 1;
  for (let i = 1; i <= num; i++) {
    [a, b] = [b, a + b];
    console.log([a , b])
  }
  return b;
}

fib(5) // 13
```

## Factorialize a Number

```javascript
// 1. Factorialize a Number With Recursion
function factorialize1(num) {
	if (num < 0)
		return -1;
	else if (num == 0)
		return 1;
	else {
		return (num * factorialize1(num - 1));
	}
}
factorialize1(5);
```

```javascript
// 2. Factorialize a Number with a WHILE loop
function factorialize2(num) {
  var result = num;
  if (num === 0 || num === 1) 
    return 1; 
  while (num-- > 1) { 
    result *= num;
  }
  return result;
}
factorialize2(5);
```

## Find out the largest number that could be generated from a  sorted array

```javascript
let largestNumber = function(nums) {
 
    const res =  nums.map(String).sort((a,b) => b.concat(a) - a.concat(b)).join('')
 
    if(res.length > 1 && res.charAt(0) == '0') {
        return '0'
    }
    else {
        return res
    }
};

largestNumber([3,30,34,5,9]) // output: 9534330
```

