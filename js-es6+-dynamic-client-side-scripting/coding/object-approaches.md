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

## Check whether two objects have the same key value

```javascript
/**
 * Check whether two objects have the same key value
 * @param {Object} a: first object
 * @param {Object} b: the first object
 * @return {Boolean} same as true, otherwise false
 */
export const isObjectEqual = (a, b) => {
    var aProps = Object.getOwnPropertyNames(a);
    var bProps = Object.getOwnPropertyNames(b);

    if (aProps.length !== bProps.length) {
        return false;
    }

    for (var i = 0; i < aProps.length; i++) {
        var propName = aProps[i];

        if (a[propName] !== b[propName]) {
            return false;
        }
    }
    return true;
}
```

