# Array Approaches

## Merge the following two array and The output should be

```javascript
/*
[
    { id: 1, name: "David", position: null },
    { id: 2, name: "John", position: "Leader" },
    { id: 3, name: "Matt", position: "Captain" },
    { id: 4, name: "Greg", position: "VP" },
    { id: 5, name: null, position: "Pawn" },
    { id: 6, name: null, position: "Rogue" }
];
*/

// Using ES6 Map
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
const result = Array.from(_hash.values()); 
```

## Write a function to rotate the array from left to right, and explain its Big-O notation.

\(P.S. Using **HOF** will be count as half scores\)  
\(P.S. And recursion is never a satisfying solution\)  
\(P.S. Surprise me by using any ADS, aka abstract data structure\)

```javascript
// e.q.: [1,2,3] ==> [3,1,2] ==> [2,3,1]

/**
\* [arrayRotation description]
\* @param  {[Array]}     arr     [The target array that passed in]
\* @param  {[Number]}     steps     [The times need to do the rotation]
\* @return {[Array]}           [Return the result array]
\*/

function arrayRotation(arr, steps) {
    // Code here...
    // Get bonus score by explain your solution's performance
}

// Test Sample:
arrayRotation([1,2,3], 2)
```

#### Solution

```javascript
// Solution: for
let rotate = function(nums, k) {
    let tempArr = [] 
    for(let i=0; i<nums.length; i++){ // Save the rotated array with a new array
        tempArr[(i+k) % nums.length] = nums[i] 
    }
    return tempArr;
};

// Solution: HOF, pop(), unshift()
let rotate = function(nums, k) {
    k %= nums.length
    for(let i = 0; i < k; i ++){
        nums.unshift(nums.pop()); // Remove the element from the end first, then put it to the front
    }
};

let rotate = function(nums, k) {
    k %= nums.length
    nums.unshift(...nums.splice(nums.length - k, k));
};
```

## Use HOF methods to accomplish a quick sort for an array.

```javascript
var array = [2,4,5,22,1,6,44,7,3,9];
const arr = [...array].map(temp => parseInt(temp, 10)).sort((a, b) => a - b);
```

## Find out the duplicated number.

```javascript
const arr = [1, 2, 3, 4, 4, 5, 6, 7, 7, 8, 6, 10];
const findDupes = arr => {
	const observed = {};
	for (let i = 0, len = arr.length; i < len; i++) {
		if (!observed[arr[i]]) {
			observed[arr[i]] = arr[i];
		}
	}
}

findDupes(arr); // Output: 4, 7, 6
```

## Find out the intersection part of following two arrays.

```javascript
let arr1 = ["mike", "sue", "tom", "kathy", "henry"],
		arr2 = ["howey", "jim", "sue", "jennifer", "kathy", "hank", "alex"];

function intersection(a, b) {
	return a.filter(e => b.indexOf(e) > -1)
}

intersection(arr1, arr2); // Output: ['sue', 'kathy']
```

## Return the maximum and minimum number in the array

```javascript
const arr = [1, 2, 3, 4, 100];
const findMaxMin = (arr) => {
  let max = arr[0];
  let min = arr[0];
  
  for(let i = 0; i < arr.length; i++) {
    if(arr[i] > max) {
      max = arr[i];
    } else if (arr[i] < min) {
      min = arr[i];
    }
  }  
  return {
    "max": max,
    "min": min
  };
}

console.log(findMaxMin(arr)); // Output: { "max": 100, "min": 1 }
```

## Return the maximum and minimum missing number in the array

```javascript
let arr = [1, 2, 6, 7, 8, 10];
const findMissingNum = (arr) => {
  let newArr = [];
  for (let i = 0, len = arr.length - 1; i < len; i++) {
    if (arr[i] + 1 != arr[i + 1]) {
    	console.log(arr[i] + 1)
      newArr.push(arr[i] + 1);
    }
  }
  return newArr;
}

console.log(findMissingNum(arr)); // Output: [3, 9]
```

