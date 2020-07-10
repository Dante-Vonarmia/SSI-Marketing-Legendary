# String Approaches

## Check the parenthesis is balanced or not.

```javascript
let isBalancedParenthesis = (str) => {
    return !str.split('').reduce((uptoPrevChar, thisChar) => {
        if (thisChar === '(' || thisChar === '{' || thisChar === '[') {
            return ++uptoPrevChar;
        } else if (thisChar === ')' || thisChar === '}' || thisChar === ']') {
            return --uptoPrevChar;
        }
        return uptoPrevChar
    }, 0);
}

// Test Cases
isBalancedParenthesis("[()]{}{[()()]()}"); // returns true
isBalancedParenthesis("[{()()}({[]})]({}[({})])((((((()[])){}))[]{{{({({({{{{{{}}}}}})})})}}}))[][][]"); // returns true
isBalancedParenthesis("({(()))}}"); // returns false
```



## A popular fuzzbuzz question.

Write a loop and output 'fizz' everytime the `i` could be mod by **3**,  
output 'buzz' everytime the `i` could be mod by **5**,  
and output 'fuzzbuzz' everytime it could be mod by **the least common multiple**.

```javascript
// Complete following part
for (let i = 0; i < 100;) 
    console.log((++i % 3 ? '' : 'fizz') + (i % 5 ? '' : 'buzz') || i);
```

