# neoG Camp - Level 1 - ES6

## Converting to ES6+

```js
var aloo = 1;
if (aloo == 1) {
   var a = 2;
   console.log(a);
}
console.log(aloo);
```

```js
let aloo = 1;
if (aloo === 1) {
    let a = 2;
    console.log(a);
}
console.log(aloo);
```

---

```js
var multiply = function(x, y) {
  return x * y;
};
```

```js
const multiply = (x, y) => x * y;
```
___
```js
var customer = {
  name: "Bhaalo"
};

var card = {
  amount: 20,
  product: "Aaalo",
  unitprice: 50
};

var message = "Hello " + customer.name + " wants to buy " +
    card.amount + " " + card.product + " for price of " +
    card.unitprice + " per piece"
```

```js
const customer = {
    name: "Bhaalo"
};

const card = {
    amount: 20,
    product: "Aaalo",
    unitprice: 50
};

const message = `Hello ${customer.name} wants to buy
    ${card.amount} ${card.product} for price of
    ${card.unitprice} per piece`;
```
___

```js
var Neog = ["Tanvi", "Swap", "Tanay", "MA", "CA", "PA", "TA"],
CEO = Neog[0],
Mentor = Neog[2];
```

```js
const Neog = ["Tanvi", "Swap", "Tanay", "MA", "CA", "PA", "TA"],
    [CEO, , Mentor] = Neog;
```

Note: revisit, is there a better way?

___

```js
var arr = ["MA", "TA", "PA", "CA"];

var firstName = arr[0],
var surname = arr[1];

console.log(firstName);
console.log(surname);
```

```js
const arr = ["MA", "TA", "PA", "CA"];

const [firstName, surname] = arr;

console.log(firstName);
console.log(surname);
```

___

```js
var Aaloo = "Tasty";
var Bhaloo = "Cute";
var Obj = {
  Aaloo: Aaloo,
  Bhaloo: Bhaloo
};
```

```js
const Obj = { Aaloo: "Tasty", Bhaloo: "Cute" };
```

___

```js
var a = 5;
var b = 10;
console.log("Fifteen is ".concat(a + b, " and not ").concat(2 * a + b, "."));
```

```js
const a = 5;
const b = 10;
console.log(`Fifteen is ${a + b} and not ${2 * a + b}`);
```

___

```js
var arithmeticsObj = {
  sum: function sum(num1, num2) {
    return num1 + num2;
  },
  multiply: function multiply(num1, num2) {
    return num1 * num2;
  }
};
```

```js
const arithmeticsObj = {
    sum: function (num1, num2) {
      return num1 + num2
    },
    multiply: function (num1, num2) {
      return num1 * num2
    }
}
```

Note: It's generally not recommended to use arrow functions within an object. ```this``` in arrow function within an object binds to the Window object (if run on browser). Traditional functions bind to the object itself.

```js
const arithmeticsObj = {
    sum: (n1, n2) => {
        console.log(this, "from sum"); // this binds to Window object
        return n1 + n2;
    },
    multiply: function multiply(n1, n2) {
        console.log(this, "from multiply"); // this binds to the current object
        return n1 * n2;
    }
}
```

___

```js
var avengers = {
  operation: "Assemble",
  members: [
    { ironMan: "Tony Stark" },
    { captainAmerica: "Steve Rogers" },
    { blackWidow: "Natasha Romanoff" }
  ]
};
var operation = avengers.operation,
  members = avengers.members;
```

```js
const avengers = {
  operation: "Assemble",
  members: [
    { ironMan: "Tony Stark" },
    { captainAmerica: "Steve Rogers" },
    { blackWidow: "Natasha Romanoff" }
  ]
};

var {operation, members} = avengers;
```

## Converting from ES6+ to ES5

```js
const packIt = (...args) => console.log(args)

packIt(1,2,3,5,5)
```

```js
function packIt() {
    let args = [];
    for (let item of arguments) {
      args.push(item);
    }
    console.log(args)
}
```

___

## Guess the Output

```js
const hello = () => "Hello"
const welcome = () => "Welcome"
const [Hello = hello(), Welcome = welcome()] = ["Namaste"]
console.log(Hello, Welcome)
```

_Namaste_

Reasoning: Right hand side of the assignment operatior has only 1 element in the array which is assigned to the first element on the left hand side.

---

```js
const obj = {
    aloo : 1,
    bhallo : 2
}

const {c : aloo = [2,3,4].push(5), aloo} = obj 

console.log(aloo)
```

_Syntax Error (aloo has already been declared)_

Reasoning: aloo is used twice as a variable. ```const``` and ```let``` don't allow us to re-declare a variable but ```var``` does. We would have not seen the error with ```var```. 
___

## Othe notes

```js
const a = 1;

a === 1 ? b = 5 : c = 10;
console.log(b);
console.log(c); // error: c is not defined
```

## Interview practice session

```js
function consoleNum() {

    var isWorkshop = true;
    var num = 10;

    if (isWorkshop) {
        let num = 20;
        console.log(num);
    }
    
    console.log(num);
}

consoleNum();
```

20<br>
10

Reasoning: there won't be a syntax error with `let num = 20` as it's in a different scope.

---

```js
function sum(a, b) {
    return a + b;
}

console.log(sum(1, '2'));
```

12

Reasoning: adding a string to a number leads to concatenation

---

```js
function sum(a, b) {
    return a + b;
}

console.log(sum(5, true));
```

6

---

TODO: Explain hoisting and TDZ.

---

What's the difference b/w `===` and `==`?

```js
let a = null;
let b;

console.log(a == b);
console.log(a === b);
```

true<br>
false

== compares the value, === compares the value as well as type

---

TODO: Why is the type of null an object?

```js
console.log(typeof null);    // object
console.log(typeof undefined);    // undefined
```

---

```js
{
    var a = 2;
    var a = 3;
    console.log(a);
}

{
    let b = 10;
    let b = 20;
    console.log(b);
}
```

3<br>
Syntax Error: Identifier 'b' has already been declared.

___

TODO: What are the differences b/w `var` and `let`?

---

```js
const myData = { name: "Akanksha", hobby: "Painting" };
myData.name = "Tanay";

console.log(myData);

myData = { name: "Tanay", hobby: "Cracking PJs" }
console.log(myData);
```

{ name: "Tanay", hobby: "Painting" }<br>
TypeError: Assignment to a constant variable.

---

Spread operator

```js
let arr1 = [4, 5, 6];
// convert to [1, 2, 3, 4, 5, 6, 7, 8]
```

```js
arr1 = [1, 2, 3, ...arr1, 7, 8];
```

---

```js
let a = [..."apple"];
console.log(a)
```

[ 'a', 'b', 'c', 'd', 'e' ]

---

```js
var arr1 = [1, 2];
var arr2 = [arr1, [3, 4]];
var arr3 = [...arr2, [7, 8]];

console.log(arr2);
console.log(arr3);
```

[ [1, 2], [3, 4] ]<br>
[ [1, 2], [3, 4], [7, 8]]

---

Destructuring

```js
var a = 1, b = 2;
// convert to es6
```

```js
const [a, b] = [1, 2];
```

---

```js
var a = 1, b = 2;
// swap a and b
```

```js
[a, b] = [b, a];
```

---