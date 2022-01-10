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
    [CEO, _, Mentor] = Neog;
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

[firstName, surname] = arr;

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
    sum: (num1, num2) => num1 + num2,
    multiply: (num1, num2) => num1 * num2
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
    console.log(arguments)
}
```

Note: revisit - is there a better way than using ```arguments```?

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

Reasoning: aloo is used twice as a variable
___