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

