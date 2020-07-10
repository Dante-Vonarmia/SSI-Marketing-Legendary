# Object Approaches

## Add missed attribute\(s\) to the object that is need, and assign them by the default value

```javascript
let arr = [{
	name: 'poojan',
	age: '30'
}, {
	name: 'Justin'
}]

function addMissingKey(arr, key, defaultVal) {
	for (let index of arr) {
		if (!index.hasOwnProperty(key)) {
			index[key] = arr[key] || defaultVal;
		}
	}
	return arr;
}

addMissingKey(arr, 'age', 'NA') 
// Output: 
​​/*
	[{
		name: 'poojan',
		age: '30'
	}, {
		name: 'Justin',
		age: 'NA'
	}]​​​​​
*/
```

