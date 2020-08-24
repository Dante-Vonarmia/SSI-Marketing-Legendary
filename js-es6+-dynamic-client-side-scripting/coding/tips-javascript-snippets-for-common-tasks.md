# Tips: JavaScript Snippets for common tasks

## 1. maxItemOfArray <a id="5e88"></a>

This one return the maximum number from an array.

```text
const maxItemOfArray = (arr) => […arr].sort((a, b) => b — a).slice(0, 1)[0];let maxItem = maxItemOfArray([3, 5, 12, 5]);
```

## 2. areAllEqual <a id="fd81"></a>

This snippet checks if all the items of a array are equal.

```text
const areAllEqual = array => array.every(item => item === array[0]);let check1 = areAllEqual([3, 5, 2]); // false
let check2 = allEqual([3, 3, 3]); // true
```

## 3. averageOf <a id="3973"></a>

This one returns the average number of the given numbers.

```text
const averageOf = (…numbers) => numbers.reduce((a, b) => a + b, 0) / numbers.length;let average = averageOf(5, 2, 4, 7); // 4.5
```

## 4. reverseString <a id="c377"></a>

This snippet reverses a string.

```text
const reverseString = str => […str].reverse().join(‘’);let a = reverseString(‘Have a nice day!’); // !yad ecin a evaH
```

## 5. sumOf <a id="5c50"></a>

This one returns the sum of the given numbers.

```text
const sumOf = (…numbers) => numbers.reduce((a, b) => a + b, 0);let sum = sumOf(5, -3, 2, 1); // 5
```

## 6. findAndReplace <a id="b67d"></a>

This snippets find a given word in a string and replace with another one.

```text
const findAndReplace = (string, wordToFind, wordToReplace) => string.split(wordToFind).join(wordToReplace);let result = findAndReplace(‘I like banana’, ‘banana’, ‘apple’); // I like apple
```

## 7. RGBToHex <a id="2b7f"></a>

This one convert a color in RGB mode to Hex.

```text
const RGBToHex = (r, g, b) => ((r << 16) + (g << 8) + b).toString(16).padStart(6, ‘0’);let hex = RGBToHex(255, 255, 255); // ffffff
```

## 8. shuffle <a id="5d97"></a>

Do you want to know how any music player can shuffle playing item? This snippet will show you how.

```text
const shuffle = ([…array]) => {
  let m = array.length;
  
  while (m) {
    const i = Math.floor(Math.random() * m — );
    [array[m], array[i]] = [array[i], array[m]];
  }  return array;
};shuffle([5, 4, 3, 6, 20]);
```

## 9. removeFalseValues <a id="4b54"></a>

This snippet removes false values from an array, which include false, undefined, NaN, empty.

```text
const removeFalseValues = arr => arr.filter(item => item);let arr = removeFalseValues([3, 4, false, ‘’, 5, true, undefined, NaN, ‘’]); // [3, 4, 5, true]
```

## 10. removeDuplicatedValues <a id="d35a"></a>

This one removes duplicated item from an array.

```text
const removeDuplicatedValues = array => […new Set(array)];let arr = removeDuplicatedValues([5, 3, 2, 5, 6, 1, 1, 6]); // [5, 3, 2, 6, 1]
```

## 11. getTimeFromDate <a id="a493"></a>

This snippet returns time in string from a Date object.

```text
const getTimeFromDate = date => date.toTimeString().slice(0, 8);let time = getTimeFromDate(new Date()); // 09:46:08
```

## 12. capitalizeAllWords <a id="7069"></a>

This one capitalizes the first letter of all words in a string.

```text
const capitalizeAllWords = str => str.replace(/\b[a-z]/g, char => char.toUpperCase());let str = capitalizeAllWords(‘i love reading book’); // I Love Reading Book
```

## 13. getDayDiff <a id="7600"></a>

This one returns the difference in days between two dates.

```text
const getDayDiff = (date1, date2) => (date2 — date1) / (1000 * 3600 * 24);let diff = getDayDiff(new Date(‘2020–04–01’), new Date(‘2020–08–15’)); // 136
```

## 14. radianToDegree <a id="8371"></a>

This one convert an angle from radian to degree.

```text
const radianToDegree = radian => (radian * 180.0) / Math.PI;let degree = radianToDegree(2.3); // 131.78
```

## 15. isValidJSON <a id="4d9b"></a>

This snippet checks if a given string is a valid JSON.

```text
const isValidJSON = string => {
  try {
    JSON.parse(string);
    return true;
  } catch (error) {
    return false;
  }
};let check1 = isValidJSON(‘{“title”: “javascript”, “price”: 14}’); // true
let check2 = isValidJSON(‘{“title”: “javascript”, “price”: 14, subtitle}’); // false
```

## 16. toWords <a id="e27b"></a>

This one is used to convert a given string into an array of words.

```text
const toWords = (string, pattern = /[^a-zA-Z-]+/) => string.split(pattern).filter(item => item);let words = toWords(‘I want to be come a great programmer’); // [“I”, “want”, “to”, “be”, “come”, “a”, “great”, “programmer”]
```

## 17. scrollToTop <a id="f8e0"></a>

If you’re at the bottom of a long page and you want to scroll up to the top quickly, this snippet can help you in a smoothly way.

```text
const scrollToTop = () => {
  const t = document.documentElement.scrollTop || document.body.scrollTop;  if (t > 0) {
    window.requestAnimationFrame(scrollToTop);
    window.scrollTo(0, t — t / 8);
  }
};
```

## 18. isValidNumber <a id="56df"></a>

This one is used to validate if a number is valid.

```text
const isValidNumber = n => !isNaN(parseFloat(n)) && isFinite(n) && Number(n) === n;let check1 = isValidNumber(10); // true
let check2 = isValidNumber(‘a’); // false
```

