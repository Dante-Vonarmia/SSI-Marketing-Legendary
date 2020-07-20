# Tips: Short and clean code 🚧

## 1. Declaring Variables Shorthand <a id="70d3"></a>

If it does not make sense, don’t declare each variable on every single line. One line is enough, save your spaces.

Instead of:

```javascript
let name;
let price = 12;
let title;
let discount = 0.3;
```

Do this:

```javascript
let name, 
    price = 12, 
    title, 
    discount = 0.3;
```

## 2. Condition Shorthand <a id="f607"></a>

Instead of:

```javascript
if (isUsernameValid === true) {}if (isExist === false) {}
```

Do this:

```javascript
if (isUsernameValid) {}if (!isExist) {}
```

## 3. Using Decimal Base Exponent <a id="ab80"></a>

1000000 can cause some bugs if you miss one or two zero. The more zero in the tail, the more attention you have to pay. Fortunately, you don’t have to do that. Instead of writing 1000000, you can just shorten it to 1e6. The **6** represents the number of zeros in the tail.

Instead of:

```javascript
let length = 10000;
for (let i = 0; i < length; i++) {}
```

Do this:

```javascript
let length = 1e4;
for (let i = 0; i < length; i++) {}
```

## 4. Default Parameters <a id="d0c3"></a>

Sometimes you have to define a function with multiple parameters. Do you need to pass all the parameters values every time you invoke the function? Not really if you initialize the default values.

Instead of:

```javascript
let generateBookObject = (name, price, discount, genre) => {
  let book = { name, price, discount, genre };
  return book;
};
let book = generateBookObject(‘JavaScript’, 12, 0.3, ‘Technology’); 
// { name: ‘JavaScript’, price: 12, discount: 0.3, genre: ‘Technology’ }
```

Do this:

```javascript
let generateBookObject = (name = ‘JavaScript’, price = 12, discount = 0.5, genre = ‘Technology’) => {
  let book = { name, price, discount, genre };
  return book;
};
// In case discount and genre are the same as the default values,
// you don’t need to pass them to the function
let book = generateBookObject(‘JavaScript’, 12); 
// { name: ‘JavaScript’, price: 12, discount: 0.5, genre: ‘Technology’ }
```

## 5. Ternary Operator <a id="6b3e"></a>

If there’s only one else in the conditional statement, shrink it to one line using **ternary**.

Instead of:

```javascript
let name = ‘Amy’;
let message;
if (name === ‘Amy’) {
  message = ‘Welcome back Amy’;
} else {
  message = ‘Who are you?’;
}
```

Do this:

```javascript
let name = ‘Amy’;
let message = name === ‘Amy’ ? ‘Welcome back Amy’ : ‘Who are you?’;
```

## 6. Short Option for Iterating a List <a id="d623"></a>

Not every case you can replace a looping method for the short one, but if it does then do it.

Instead of:

```javascript
let names = [‘Amy’, ‘James, ‘David’, ‘John’];
for (let i = 0; i < names.length; i++) {}
```

Do this:

```javascript
let names = [‘Amy’, ‘James, ‘David’, ‘John’];
for (let name of names) {}
```

In case the indexes matter:

```javascript
let names = [‘Amy’, ‘James, ‘David’, ‘John’];
for (let [index, name] of names.entries()) {}
```

## 7. Minimal Evaluation <a id="b9ae"></a>

You have to make sure variables are OK \(by OK I mean it’s not null or undefined\) before using them for any calculation.

For this case, **if … else** is a good option, but using **minimal evaluation** should be better.

Instead of:

```javascript
let book = {
  name: ‘Learn JavaScript’,
  price: 15
};
let finalPrice;
if (book.discount !== undefined || book.discount !== null) {
  finalPrice = book.price — book.price * book.discount;
}
```

Do this:

```javascript
let book = {
  name: ‘Learn JavaScript’,
  price: 15
};
let finalPrice = book.price — book.price * (book.discount || 0);
```

## 8. Declaring Objects Shorthand <a id="7acc"></a>

This is in case you want to define properties of an object using existing variables.

```javascript
let name = ‘Amy’;
let age = 28;
let person = { name, age }; // { name: ‘Amy’, age: 28 }
```

Note that the property’s name is the same as the existing variable’s name.

## 9. Using Arrow Function <a id="0e7c"></a>

It’s a great way to significantly reduce several lines of code.

Instead of:

```javascript
function add(a, b) {
  return a + b;
}
collection.map(item => {
  console.log(item);
});
```

Do this:

```javascript
let sum = (a, b) => a + b;
collection.map(item => console.log(item));
```

## 10. String to Number Conversion Shorthand <a id="17b1"></a>

Instead of:

```javascript
let string = ‘2020’;
let number = parseInt(string);
```

Do this:

```javascript
let string = ‘2020’;
let number = +string;
```

## 11. Using Destructuring <a id="befe"></a>

You don’t need to assign one by one to variables when you want to extract object property values. Use destructuring.

Instead of:

```javascript
let company = {
  name: ‘Apple’,
  industry: ‘Technology’,
  CEO: ‘Tim Cook’,
  stockPrice: 364,
  products: [‘iPhone’, ‘Macbook’, ‘Apple Watch’]
};
let name = company.name;
let stockPrice = company.stockPrice;
let products = company.products;
```

Do this:

```javascript
let { name, stockPrice, products } = company;
// In case you want to use different variable name. 
// For example, companyName instead of name
let { name:companyName, stockPrice, products } = company;
```

## 12. Template Strings <a id="3764"></a>

Instead of:

```javascript
let name = ‘Amy’;
let time = ‘yesterday’;
let welcomeMessage = ‘Welcome back ‘ + name + ‘. Your last time is ‘ + time;
```

Do this:

```javascript
let name = ‘Amy’;
let time = ‘yesterday’;
let welcomeMessage = `Welcome back ${name}. Your last time is ${time}`;
```

{% hint style="info" %}
Note: **welcomeMessage** is using **back-tick** \(\`\), not **apostrophe** \(‘\) nor **quotation** \(“\).
{% endhint %}

## 13. Math.pow\(\) Shorthand <a id="5929"></a>

Instead of:

```javascript
let result = Math.pow(3, 5); // 243
```

Do this:

```javascript
let result = 3**5; // 243
```

## 14. Using Back-ticks for Multi-line String <a id="5dfa"></a>

Instead of:

```javascript
let greeting = ‘Hi, I am Amy\n’
             + ‘I am a programmer.\n’
             + ‘Nice to meet you.’;
```

Do this:

```javascript
let greeting = `Hi, I am Amy
 I am a programmer.
 Nice to meet you.`
```

## 15. Using Spread to Append Things <a id="9de5"></a>

Instead of:

```javascript
let arr1 = [3, 5, 1];
let arr2 = [2, 4, 8];
let result = arr1.concat(arr2);
```

Do this:

```javascript
let arr1 = [3, 5, 1];
let result = [...arr1, 2, 4, 8]// Or even at any index you want
let result = [2, ...arr1, 4, 8]// You can also use spread with objects
let person = {
  name: ‘Tony’,
  age: 43
};
let superHero = {
  heroName: ‘Ironman’,
  ...person
};
```

