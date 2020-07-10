# Function Approaches

## Write a sample of callback function

```javascript
function writeBlog(topic, callback) {
    console.log(`Starting my ${topic} blog.`);
    // then execute the callback function that was passed
    callback();
}

writeBlog('JS', function() {
    console.log('Finished my blog!');
});
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

## Function throttle

```javascript
/**
 * Function throttle
 * @param  {Function} fn: function to execute
 * @param  {number} time: Timestamp
 * @param  {number} interval: interval time
 */
export const debouncer = (fn, time, interval = 200) => {
    if (time - (window.debounceTimestamp || 0) > interval) {
        fn && fn();
        window.debounceTimestamp = time;
    }

```

