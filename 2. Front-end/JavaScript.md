# 💜 JavaScript Basics

> 5 basic types:
>
> 1. number
> 2. string
> 3. boolean
> 4. null
> 5. undefined

## 1. Numbers

in JavaScript, we only have one number type.

`+ - * / % **`

`NaN`

👉 It is number type, but represent sth that is not a number.

```js
0 / 0;
// NaN
typeof NaN;
//number
NaN * 123;
//NaN
```

## 2. Variables

3 ways to create variable:

```js
let variable1 = 2;

const variable2 = 3; // more useful when using array & objects 💜

var variable3 = 3; // we don't use it in new javascript code
```

**increment operator**: `i++` vs. `++i`

```js
let i = 3;
let result = i++;
result; //3

let i = 3;
let result = ++i;
result; //4
```

## 3. Boolean

## 4. string

When adding a string and a number, JS turns the number into a string and smushes them together.

### 🌷 string method()

with a ( ), it is a method, without it is a property, such as `XXXX.length`

```js
let msg = "hello, i am fanpeng";
msg.toUpperCase(); //'HELLO, I AM FANPENG '

let msg = "hello, i am fanpeng          ";
msg.trim(); //'hello, i am fanpeng'
```

`replace()`

`slice()`

`indexOf()`

`repeat()`

### 🌷 template literal

```js
`hello`; //backtick string (it can interpolation)
("hello");
```

## 5. null & undifined

## 6. Math object

```js
Math.round(2.2); //2

Math.round(2.8); //3

Math.PI;

Math.abs(-456); //456

Math.pow(2, 5); //32

Math.floor(3.999); //3
```

### 🌷 Random numbers

```js
Math.random();
```

give a random number between 0 and 1

```js
const step1 = Math.random(); //0.596868984938493

const step2 = step1 * 10; //5.96868984938493

const step3 = Math.floor(step2); //5

const step4 = step3 + 1;
//6
```

we can generate a number between 1 and 10.

<br>

# 💜 Making Decisions with Boolean Logic

## 1. Comparison operators

`> < >= <= == != === !==`

`==` checks for value equality, not types. Which can lead to confusion👇

```js
1 == 1; // true
1 == "1"; // true
0 == " "; // true
null == undefined; // true
```

## 2. `if` statement

- if
- else if
- else

### 🌷 nesting conditions

```js
const password = prompt("Enter a new passoword here:");

if (password.length >= 6) {
  if (password.indexOf(" ") === -1) {
    console.log("Valid password.");
  } else {
    console.log("Password cannot contain space.");
  }
} else {
  console.log("Password is too short.");
}
```

### 🌷 Truthy & Falsy

falsy values:

- false
- 0
- "" empty string
- null
- undefined
- NaN

Everything else is truthy.

### 🌷 Logical Operators

```js
&& //and
|| //or
!  //not
```

```js
// && every side should be true:
const password = prompt("Enter a password here: ");

if (password.length >= 6 && password.indexOf(" ") === -1) {
  console.log("Valid password.");
} else {
  console.log("Incorrect format.");
}
```

```js
// || one side should be true:
const age = prompt("Enter your age: ");

if (age < 5 || age > 65) {
  console.log("Free!");
} else if (age < 10) {
  console.log("$10");
} else if (age < 65) {
  console.log("$20");
}
```

```js
// ! not
!false; //true
!null; //true
```

### 🌷 Switch statement

(not commonly used)

```js
const day = 3;
switch (day) {
  case 1:
    console.log("Monday");
    break;
  case 2:
    cosnole.log("Tuesday");
    break;
  default:
    console.log("I don't know that.");
}
```

# 💜 Array (data structure)

## 1. Array methods

> `array`: **Ordered** collection of values.

We can see the index here:

<img src="../images/Front-end/array.png" alt="array" width="700">

### 🌷 `push()` & `pop()`

- `push()` add to the end
- `pop()` remove the end

```js
let movieLine = ["tom", "nancy"];

movieLine.push("oliver"); // ["tom","nancy","oliver"]

movieline.pop(); // ["tom","nancy"]
```

### 🌷 `shift()` & `unshift()`

- `shift()` remove the beginning
- `unshift()` add to the beginning

```js
let movieLine = ["tom", "nancy", "pablo", "oliver"];

movieLine.shift(); // ["nancy", "pablo", "oliver"]

movieLine.unshift("VIP"); // ["VIP", "nancy", "pablo", "oliver"]
```

### 🌷 `concat()` & `includes()` & `reverse()`

```js
let cats = ["dodo", "shadow"];
let dogs = ["orea", "cloud"];
let catAndDog = cats.concat(dogs); //["dodo", "shadow", "orea", "cloud"]
// ⭐️ but the cats and dogs are not changed

cats.includes("dodo"); //true

catAndDog.reverse(); //["cloud", "orea", "shadow", "dodo"]
catAndDog; // ["cloud", "orea", "shadow", "dodo"]
// ⭐️ the reverse() changed the original array
```

### 🌷 `slice()` & `splice()`

`slice()` require the start and the end, but optional

```js
let color = ["red", "blue", "green", "yellow", "purple", "black", "white"];

color.slice(3); // ["yellow", "purple", "black", "white"]

color.slice(2, 4); // ["green", "yellow"]
```

`splice()` require the start, deletecount and items to be added

```js
let color = ["red", "blue", "green", "yellow", "purple", "black", "white"];

color.splice(1, 0, "pink"); //["red", "pink", "blue", "green", "yellow", "purple", "black", "white"]
```

### 🌷 `sort()`

default sort order is ascending, which compare the UTF-16 code.

## 2. Referfencing

```js
[] === []; // false
[1, 2] === [1, 2]; //false
```

why?

> when creating an array, JS allocate the special memory for it, they are distinct. They are not referring to the same thing in memory.

here, num and numCopy are referring to the same array:

```js
let num = [1, 2, 3];
let numCopy = num;
num.push(4);
num; // [1, 2, 3, 4]
numCopy; //[1, 2, 3, 4]
num === numCopy; // true
```

## 3. Array and Const

the arrary points to a place:

```js
const nums = [1, 2, 3];
nums.push(4); //[1, 2, 3, 4]
```

its like : the box stay the same, but the eggs (content) change

<img src="../images/Front-end/array and const.png" alt="array and const" width="800">

<br>

# 💜 Object (data structure)

> objects are collections of properties.
>
> properties are **key-value** pairs.

Create object literals:

```js
const year = {
  1999: "good",
  2000: "bad",
  nextYear: "maybe good",
};

year.1999; // "good"
year["1999"]; // "good"
```

⭐️ Tip: all keys are converted to strings unless they are Symbols.

⭐️ Tip: When Access values: can use dot `.` or `[""]`

<br>

# 💜 Loop

## 1. `for` loop

```js
for (let i = 1; i <= 10; i++) {
  console.log(i);
}
```

loop over array:

```js
const animal = ["cat", "dog", "cow", "bird"];

for (let i = 0; i < animal.length; i++) {
  console.log(animal[i]);
}
```

### 🌷 nested for loop

```js
for (let i = 1; i <= 10; i++) {
  console.log(`i is: ${i}`);
  for (let j = 1; j < 4; j++) {
    console.log(`j is: ${j}`);
  }
}
```

## 2. `while` loop

it is useful when unknown times of loop.

**`break`** keyword:

```js
let input = prompt("Hi, enter somethign: ");
while (true) {
  input = prompt(input);
  if (input.toLowerCase() === "stop copying me") break;
}
console.log("You win.");
```

A number guessing game:

```js
let maximum = parseInt(prompt("Enter a nubmer: ")); //parseInt convert a string num to a number

Math.floor(Math.random() * 10) + 1;
```

## 3. `for...of` loop

A easy way of iterating array or other objects.

```js
let animals = ["cat", "dog", "cow", "rabbit", "pig"];

for (let animal of animals) {
  console.log(animal);
}
```

```js
let name = "lisa";
for (let char of name) {
  console.log(char);
}
```

### 🌷 iterate `object` with `for...in`

```js
const testScores = {
  tom: 80,
  damon: 67,
  kim: 89,
  shawn: 91,
};

for (let person in testScores) {
  console.log(person);
}
// tom, damon...

// it gives us all the keys in the object
```

or we can use `Object.keys(testScores)` to get all the keys, `Object.values(testScores)`, `Object.entries(testScores)`

<br>

# 💜 Functions

## 1. Basics

### 🌷 define & run

> Functions are **Resuable** chunk of code.
>
> 2 steps:
>
> - define the function
> - run it

```js
//define:
function funcName() {
  "do something";
}

funcName(); //run
```

### 🌷 arguments

functions that accept inputs.

```js
// no arguments:
"hello".toUpperCase();

// with arguments:
"hello".indexOf("o");
```

⭐️ Tip: parameter is like the placeholder when define the function, arguments are the actual value we pass into the function when the function is called.

⭐️ Tip: the order of the arguments matters.

### 🌷 Return (built-in method)

- `return` can store values.
- `return` ends functions execution

## 2. More about Functions

### 🌷 function scope

> means variable visibility

```js
let totalEggs = 0;
function collectEggs() {
  totalEggs = 6;
}
console.log(totalEggs); // 0
collectEggs();
console.log(totalEggs); // 6
```

### 🌷 block scope

```js
let radius = 8;
if (radius > 0) {
  const PI = 3.14159;
  let msg = "Hi";
}

console.log(radius); // 8
console.log(msg); // not defined error
```

```js
for (let i = 0; i < 5; i++) {
  let msg = "asdfasdf";
}
console.log(msg); // not defined error
```

### 🌷 lexical scope

child function has access to the parent function variable.

but, parent function does not have access to the variable from child function.

```js
function bankRob() {
  const heroes = ["spiderman", "batwoman", "black panther"];
  function cryForHelp() {
    for (let hero of heroes) {
      console.log(`Please help us: ${hero.toUpperCase()}`);
    }
  }
  cryForHelp();
}
```

### 🌷 function expression

store a no name function in a variable:

```js
const add = function (x, y) {
  return x + y;
};
```

### 🌷 higher order function

1. accept other function as arguments

```js
function callTwice(func) {
  func();
  func();
}

function rollDie() {
  const roll = Math.floor(Math.random() * 6) + 1;
  console.log(roll);
}

callTwice(rollDie); // notice here we are not passing rollDie()
```

2. return a function

### 🌷 define a method

every function is a method

```js
const myMath = {
  PI: 3.14159,
  square: function (num) {
    return num * num;
  },
}; // the function keyword can be omitted: square(num) {return num * num}

myMath.square(3);
```

### 🌷 `this` keyword

1. use `this` to access other property on the same object:

```js
const cat = {
  name: "lily",
  color: "white",
  meow() {
    console.log("this.color"); // white
  },
};
```

2. here, we are actually bonding the `meow2()`to the window object:

```js
const meow2 = cat.meow;
```

### 🌷 try / catch

it prevent the code from crashing:

```js
try {
  hello.toUpperCase();
} catch {
  console.log("error");
}
```

<br>

# 💜 Callback & Array methods

> A callback function is a function passed into another function as an argumen.

## 1. `foreach()` method

```js
const numbers = [1, 2, 3, 4, 5];

numbers.foreach(function (num) {
  console.log(num);
});
```

## 2. `map()` method

**creates a new array** with the results of calling a provided function on **every element** in the calling array.

```js
const numbers = [1, 2, 3, 4, 5];

const double = numbers.map(function (num) {
  return num * 2;
});
```

## 3. arrow function

```js
const add = function (x, y) {
  return x + y;
};

// same as:

const add = (x, y) => {
  return x + y;
};
```

```js
// with single parameter, the () can be omitted
const greet = (x) => {
  return `Hey ${x}!`;
};

// arrow function without a parameter:

const rollDie = () => {
  return Math.floor(Math.random() * 10) + 1;
};
```

### 🌷 implicit return

```js
// if we have only one expressionf or return, we can use implicit return:
const rollDie = () => Math.floor(Math.random() * 6) + 1;
// ⭐️ Tip: if the line is too long, we can use the () for the return value

// for shorter ones, we can put them on one line:
const add = (a, b) => a + b;
```

## 4. `setTimeout` & `setInterval`

```js
console.log("Hello!");
setTimeout(() => console.log("are you still there..."), 3000);
console.log("Goodbye!");

// Hello
// Goodbye
// are you still there...
```

```js
const id = setInterval(() => {
  console.log(Math.random());
}, 2000);
// clearInterval(id)
```

## 5. `filter()` method

**create a new array** with the elements that **pass the test** provided by the function:

```js
const nums = [9, 8, 7, 6, 5];
const odds = nums.filter((n) => {
  return n % 2 === 1; //if true, n is added to the new array
});
// [9, 7, 5]
```

## 6. `.some()` & `.every()` method

boolean method

`some()`: return true if any of the elements pass the test in the function;

`every()`: return true only when all the elements pass the test in the function.

```js
const exams = [76, 55, 87, 79, 90, 68];

exams.every((score) => score > 75); // false

exams.some((score) => score > 75); // true

const allEvens = (numbers) => numbers.every((num) => num % 2 === 0);
```

## 7. `reduce()`

```js
const prices = [91, 23, 55, 32, 20];
let total = 0;
for (let price of prices) {
  total += price;
}

// this is equal to:👇

const prices = [91, 23, 55, 32, 20];
const sumPrice = prices.reduce((total, price) => {
  total + price;
});
```

```js
// finding the minimum of the array:
const numbers = [3, 43, 6, 7, 89, 9];

const minNum = numbers.reduce((min, num) => {
  if (num < min) {
    return num;
  }
  return min;
});
```

```js
// reduce() can have a second argument:
const numbers = [2, 4, 6, 8];
numbers.reduce((sum, num) => sum + num, 100); // here, we added 100 to it
// 120
```

## 8. arrow function & `this`

🌷 **confusing here**:

```js
const person = {
  firstName: "tom",
  lastName: "jackson",
  fullName: function () {
    return `${this.firstName} ${this.lastName}`;
  },
  shoutName: function () {
    setTimeout(() => {
      console.log(this);
      console.log(this.fullName());
    }, 3000);
  },
};
```

<br>

# 💜 New features

## 1. default params

```js
function rollDie(sides = 6) {
  return Math.floor(Math.random() * sides) + 1;
}
```

## 2. spread

### 🌷 spread in function calls

```js
const nums = [12, 2, 4, 5, 7, 87, 45.34, 7, 67];
console.log(...nums); // 12 2 4 5 7 87 45.34 7 67
// we got the nums with spaces

console.log("hello"); // hello
console.log(..."hello"); // h e l l o
```

### 🌷 spread with array literals

```js
const cats = ["Whiskers", "Fluffy", "Mittens", "Oreo"];
const dogs = ["Buddy", "Max", "Daisy", "Charlie"];

const allPets = [...cats, ...dogs];
// ["Whiskers", "Fluffy", "Mittens", "Oreo", "Buddy", "Max", "Daisy", "Charlie"];

const allPets = ["Happy", ...cats, ...dogs]; // ["Happy", "Whiskers", "Fluffy", "Mittens", "Oreo", "Buddy", "Max", "Daisy", "Charlie"]
```

```js
// we can also spread string:
["hello"];
[..."hello"]; // ["h", "e", "l", "l", "o"]
```

### 🌷 spread with object

```js
const cat = { legs: 4, family: "yellow" };
const dog = { isFurry: true, family: "blue" };

const catDog = { ...cat, ...dog }; // {legs: 4, family: 'blue', isFurry: true}
// the two are combined but the order matters

const catDog = { ...cat, ...dog, family: "pink" }; // we can also modify it
// {legs: 4, family: 'pink', isFurry: true}
```

```js
// spread array into object

{...[2,3,4,5]} // {0: 2, 1: 3, 2: 4, 3: 5}
```

## 3. rest params

different with spread, it allows us to pass a variable number of arguments to a function as an array.

```js
function sum(...numbers) {
  let total = 0;
  for (const number of numbers) {
    total += number;
  }
  return total;
}

console.log(sum(1, 2, 3, 4, 5)); // 15
```

## 4. destructuring

### 🌷 with array

```js
const raceResults = ["Eliud", "Feyisa", "Galen"];
const [gold, silver, bronze] = raceResults;
gold; // "Eliud"
silver; // "Feyisa"
bronze; // "Galen"
```

we can also use ...to include others:

```js
const scores = [12312, 24234, 5345, 465345, 37356];
const [gold, silver, bronze, ...everyoneElse] = scores;
// everyoneElse: [465345, 37356]
```

We can also access the value at any index in an array with commas:

```js
const [a, b, , , c] = [1, 2, 3, 4, 5, 6];

console.log(a, b, c); // 1, 2, 5
```

exchange the value:

```js
let a = 8,
  b = 6;

[a, b] = [b, a];
```

### 🌷 with object

we can make variables from the properties:

```js
const person = {
  firstName: "John",
  lastName: "Doe",
  born: 1999,
};

const { firstName, lastName, born } = person;

console.log(firstName); // John
console.log(lastName); // Doe
console.log(born); // 1999
```

we can also rename the variable when assignment:

```js
const person = {
  firstName: "John",
  lastName: "Doe",
  born: 1999,
};

const { born: birthYear } = person;

console.log(birthYear); // 1999
```

Assign Variables from Nested Object:

```js
const user = {
  johnDoe: {
    age: 34,
    email: "johnDoe@freeCodeCamp.com",
  },
};

const {
  johnDoe: { age, email },
} = user;
```

### 🌷 with params

```js
function printFullName({ firstName, lastName }) {
  console.log(`${firstName} ${lastName}`);
}

const person = {
  firstName: "John",
  lastName: "Doe",
};

printFullName(person); // John Doe
```

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

# 7. JSON built-in object (javascript object notation)

JSON only uses `“”` and it does not support functions. we use JSON when sending data between computers and store data.

here, we converted the object into the JSON format string, and the method will be lost:

```js
const myObject = {
  name: "Fanpeng",
  hobbies: ["reading", "coding", "swimming"],
  hello: function () {
    console.log("hello!");
  },
};

console.log(myObject);
// {
//     name: 'Fanpeng',
//     hobbies: [ 'reading', 'coding', 'swimming' ],
//     hello: [Function: hello]
// }
console.log(myObject.name); // Fanpeng
myObject.hello(); //hello!
console.log(typeof myObject); // object

const sendJSON = JSON.stringify(myObject);
console.log(sendJSON); // {"name":"Fanpeng","hobbies":["reading","coding","swimming"]}
console.log(typeof sendJSON); // string
console.log(sendJSON.name); // undefined
```

convert JSON into JS (we can notice here the method was lost):

```javascript
const receiveJSON = JSON.parse(sendJSON);
console.log(receiveJSON);
//{name: "Fanpeng", hobbies: Array(3)}
console.log(reveiveJSON);
//object
```

# 8. Local storage

all variables are temporary, when refreshing the page, the storage will lost.

Local storage will not clear the variables when refreshing, but **it only support strings:**

# 9. DOM (built-in document object model)

the DOM combines JS and HTML together, and we can have HTML elements inside JS, HTML will converted to JS object. it gives control of JS to the webpage.

**window (built-in object) ——the webpage**

```js
window.console;
window.document;
window.alert;
```
