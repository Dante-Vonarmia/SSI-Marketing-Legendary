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
      newArr.push(arr[i] + 1);
    }
  }
  return newArr;
}

console.log(findMissingNum(arr)); // Output: [3, 9]
```

## Find out all the pairs that equal to the same summation

```javascript
let arr = [1, 5, 6, 1, 2, 3, 0, 1];
const findSumPairs = (arr, value) => {
  let sumsLookup = {};
  let output = [];

  for (let i = 0; i < arr.length; i++) {
    let targetVal = value - arr[i];

    if (sumsLookup[targetVal]) {
      output.push([arr[i], targetVal]);
    }

    sumsLookup[arr[i]] = true;
  }

  return output;
}

console.log(findSumPairs(arr, 6)); // Output: ​​​​​[ [ 5, 1 ], [ 1, 5 ], [ 0, 6 ], [ 1, 5 ] ]​​​​​
```

## The element with the most occurrences and the number of times.

```javascript
// Find out the number's occurrences
function countOfElement(arr, N) {
  let encounteredNums = {};
  let num;
  for (let i = 0; i < arr.length; i++) {
    num = arr[i];
    if (encounteredNums[num]) {
      // value already encountered, count++
      encounteredNums[num]++;
    } else {
      // first encounter, initialize count
      encounteredNums[num] = 1;
    }
  }
  return {
    element: N,
    times: encounteredNums[N]
  } || 0; // 6 times
  // return encounteredNums[N] || 0; // 2
}
// returns 6
countOfElement([3, 4, 2, 3, 2, 2, 2, 2, 3, 2], 2); // Output:​​​​​ { element: 2, times: 6 }​​​​​


// Find out the most Occurred number
let arr = [1,2,2,3,4,4,4,5,5,5,5,5,5,6,7,8,8,9];

function mostOccur(arr) {
  // if (arr) { ... } // common error check
  
  let temp = {},
      result = 0;
            
  for (let i = 0, length = arr.length; i < length; i++) {
    if (temp[arr[i]]) {
      temp[arr[i]]++;
    } else {
      temp[arr[i]] = 1;
    }
    if (temp[arr[i]] > result) {
      result = arr[i]
    } 
  }
      
  return result;
}

mostOccur(arr) // Output: 5
```

## Find the number n greatest number in an array.

```javascript
function Kth_greatest_in_array(arr, k) {

	for (var i = 0; i < k; i++) {
		var max_index = i,
			tmp = arr[i];

		for (var j = i + 1; j < arr.length; j++) {
			if (arr[j] > arr[max_index]) {
				max_index = j;
			}
		}

		arr[i] = arr[max_index];
		arr[max_index] = tmp;
	}

	return arr[k - 1];
}

console.log(Kth_greatest_in_array([1, 2, 6, 4, 5], 1))

// Ouput: 
// [1, 2, 6, 4, 5], 1 => 6;
// [1, 2, 6, 4, 5], 2 => 5;
// [1, 2, 6, 4, 5], 3 => 4;
```

## Meandering Array

```javascript
let arr = [7, -5, 2, 7, 8, -2, 25, 25];
let result = [];

function meandering(arr) {
    if (!arr.length)
        return arr;
    arr.sort((prev, cur) => prev - cur);
    for (var i = 0, j = arr.length - 1; i <= j; i++, j--) {  
        result = [...result, arr[j]];
        result = [...result, arr[i]];

        if (i === j) 
            result = [...result, arr[i]];
    }
    return result
}

console.log(meandering(arr)); // Output: ​​​​​[ 25, -5, 25, -2, 8, 2, 7, 7 ]​​​​​
```

## Find out the duplicated number that need to be remove. \(Not all the element need to be removed\)

```javascript
const arr = [1, 1, 3, 1, 3, 1, 5];
const removeDupes = (arr) => {
  let result = [];
  for (let i = 0, len = arr.length; i < len; i++) {
    if (result.indexOf(arr[i]) < 0) {
      result.push(arr[i]);
    }
  }
  return result;
}

console.log(removeDupes(arr)); // Output: [1, 3, 5]
```

## Check whether the "a" array contains the "b" array

```javascript
export const getArrRepeat = (arr1, arr2) => arr1.filter((item, index) => arr2.includes(item))
```

