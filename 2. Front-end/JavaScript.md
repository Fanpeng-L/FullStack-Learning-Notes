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

⭐️ `if` statement creates **new scope**. the variable created within the scope cannot be accessed outside of the scope.

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

`splice()` require the start, deletecount and items

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

⭐️ all keys are converted to strings unless they are Symbols.

⭐️ When Access values: can use dot `.` or `[""]`

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

A easy way of iterable array.

```js
let animals = ["cat", "dog", "cow", "rabbit", "pig"];

for (animal of animals) {
  console.log(animal);
}
```

# 5. Functions

we can reuse the code:

```html
<script>
  function function1() {
    console.log("hello");
    console.log(2 + 2);
  }

  function1();
</script>
```

return a variable is preferred to a global variable, to avoid scope conflict.

`parameter` is like a variable that is saved in the function.

```html
<script>
  function calculatorTax(cost, taxPercent) {
    console.log(cost * taxPercent);
  }

  calculatorTax(4000, 0.2);
  calculatorTax(3000, 0.1);
</script>
```

We can also set the default value for the parameter: so if the parameter value was not provided, it will pass the default value.

```html
<script>
  function calculatorTax(cost, taxPercent = 0.1) {
    console.log(cost * taxPercent);
  }

  calculatorTax(4000, 0.2);
  calculatorTax(3000);
</script>
```

# 6. Objects

an object example:

```html
<script>
  const product = {
    name: "socks",
    price: 1090,
  };
  console.log(product);
  console.log(product.name);
  console.log(product["name"]); //bracket notation. does the same thing as dot.

  product.name = "cotton socks"; //change the value to a new one
  console.log(product);

  product.newProperty = ture;
  console.log(product);

  delete product.newProperty;
  console.log(product);
</script>

// {name: 'socks', price:1090} // socks // {name: 'cotton socks', price:1090} //
{name: 'cotton socks', price:1090, newProperty: true} // {name: 'cotton socks',
price:1090}
```

Nested object:

```html
<script>
  const product = {
    name: "socks",
    rating: {
      stars: 4.5,
      count: 87,
    },
  };
  console.log(product.rating.count);

  product.name = "cotton socks"; //change the value to a new one
  console.log(product);
</script>
```

we can also put the function into an object:

```html
<script>
       const product = {
         name: "socks",
         rating: {
      stars: 4.5,
             count: 87
         }
  fun: function function1() {
  	    console.log("function inside object");
  }
       };
       console.log(product.rating.count)
       product.fun();
</script>
```

## Objects are references

even we create the object with `const`, we can still change the value inside of the object. when comparing 2 objects, we are comparing the references not the values inside.

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

```html
localStorage.getItem('message'); localStorage.setItem('message', 'hello');
//save in local storage localStorage.removeItem('message');
```

# 9. DOM (built-in document object model)

the DOM combines JS and HTML together, and we can have HTML elements inside JS, HTML will converted to JS object. it gives control of JS to the webpage.

`document.body`

`document.title`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Dom</title>
  </head>

  <body>
    <button>hello</button>

    <script>
      document.body.innerHTML = "hello";
      document.body.innerHTML = "<button>Good Job!</button>";
      document.title = "Good job!";
    </script>
  </body>
</html>
```

`document.querySelector()`

it can get any element from the page and put it inside JS.

`<input/>`

`<input/>` `innerHTML` `onkeydown=””`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Dom project</title>
  </head>

  <body>
    <p>YouTube Subscribe Button</p>
    <button onclick="subscribe();" class="js-subscribe-button">
      Subscribe
    </button>

    <p>Amazon Shipping Calculator</p>

    <input
      placeholder="Cost of order"
      class="js-cost-input"
      onkeydown="handleCostKeydown(event)"
    />

    <button onclick="calculateTotal();">Calculator</button>
    <p class="js-total-cost"></p>

    <script>
      function handleCostKeydown(event) {
        if (event.key === "Enter") {
          calculateTotal();
        }
      }

      function calculateTotal() {
        const inputElement = document.querySelector(".js-cost-input");
        let cost = Number(inputElement.value);

        if (cost < 40) {
          cost += 10;
        }

        document.querySelector(".js-total-cost").innerHTML = `$${cost}`;
      }
      function subscribe() {
        const buttonElement = document.querySelector(".js-subscribe-button");

        if (buttonElement.innerText === "Subscribe") {
          buttonElement.innerText = "Subscribed";
        } else {
          buttonElement.innerText = "Subscribe";
        }
      }
    </script>
  </body>
</html>
```

to get value in the input: `.value`

```html
<!DOCTYPE html>
<html>
  <head></head>
  <body>
    <input
      placeholder="Name"
      class="js-name-input"
      onkeydown="
        if (event.key === 'Enter') {
          const inputElement = document.querySelector('.js-name-input');
          document.querySelector('.js-message')
            .innerHTML = `Your name is: ${inputElement.value}`;
        }
      "
    />

    <button
      onclick="
      const inputElement = document.querySelector('.js-name-input');
      document.querySelector('.js-message')
        .innerHTML = `Your name is: ${inputElement.value}`;
    "
    >
      Submit
    </button>

    <p class="js-message"></p>
  </body>
</html>
```

**window (built-in object) ——the webpage**

```html
window.console window.document window.alert
```

# 10. Arrays & Loops

```html
<script>
  const myArray = [10, 20, 30];
  console.log(myArray);

  myArray.length;
  myArray.push(100);
  myArray.splice(0, 2);

  let i = 1;
  while (i <= 5) {
    console.log(i);
    i += 1;
  }

  for (let i = 1; i <= 5; i++) {
    console.log(i);
  }

  const todoList = ["make dinner", "wash dishes", "watch youtube"];

  for (let i = 0; i < todoList.length; i++) {
    console.log(todoList[i]);
  }

  const nums = [10, 20, 30];
  nums[nums.length - 1] = 99;
  console.log(nums);

  const nums = [1, 2, 3];
  let total = 0;

  for (let i = 0; i < nums.length; i++) {
    const num = nums[i];
    total += num;
  }
  console.log(total);

  const numsDoubled = [];
  for (let i = 0; i < nums.length; i++) {
    const num = nums[i];
    numsDoubled.push(num * 2);
  }
</script>
```

```js
const todoList = ["make dinner", "wash dishes"];

renderTodoList();

function renderTodoList() {
  let todoListHTML = "";

  for (let i = 0; i < todoList.length; i++) {
    const todo = todoList[i];
    const html = `<p>${todo}</p>`;
    todoListHTML += html;
  }
  console.log(todoListHTML);

  document.querySelector(".js-todo-list").innerHTML = todoListHTML;
}

function addTodo() {
  const inputElement = document.querySelector(".js-name-input");
  const name = inputElement.value;

  todoList.push(name);

  inputElement.value = "";

  renderTodoList();
}
```

```html
<script>
  function minMax(nums) {
    const result = { min: nums[0], max: nums[0] };

    for (let i = 0; i < nums.length; i++) {
      const value = nums[i];

      if (value < result.min) {
        result.min = value;
      }

      if (value > result.max) {
        result.max = value;
      }
    }
    return result;
  }
</script>
```

if we don’t want to change the original array, we can make a copy of array1 using `.slice()` method:

```html
//other ways to get the value from the array: const [firstValue, secondValue] =
[1,2,3];
```

```js
for (let i = 1; i <= 10; i++) {
  if (i === 3) {
    continue; // which can skip number 3
  }
  console.log(i);
  if (i === 8) {
    break; // which can stop the program
  }
}
```

# 11. setTimeout() setInterval()

`setTimeout()`

a feature allows us to run a function in the future.

it will trigger asynchronous code:

computer won’t wait for a line to finish before going to the next line.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <script>
      setTimeout(function () {
        console.log("timeout");
      }, 3000);
    </script>
  </body>
</html>
```

`setInterval()`

keep running the code for certain amount of time:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <script>
      setInterval(function () {
        console.log("interval");
      }, 3000);
    </script>
  </body>
</html>
```

another way to loop through array

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <script>
      ["make dinner", "wash dishes", "watch youtube"].forEach(function (value) {
        console.log(value);
      });
      ["make dinner", "wash dishes", "watch youtube"].forEach(function (v, i) {
        console.log(v);
        console.log(i);
    </script>
  </body>
</html>
```

but in `forEach` style loop, we can only use `continue`, we can no longer use `break` to exit the loop.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <script>
      ["make dinner", "wash dishes", "watch youtube"].forEach(function (v, i) {
        if (v === "wash dishes") {
          return;
        }
        console.log(v);
        console.log(i);
      });
    </script>
  </body>
</html>
```

# Arrow function

mostly work the same way as normal function

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <script>
      const regularFunction = function () {
        console.log("hello");
      };

      const arrowFunction = () => {
        console.log("hello");
      };

      regularFunction();
      arrowFunction();
    </script>
  </body>
</html>
```

# .forEach()

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <script>
      function countPositive(nums) {
        let positiveNumbers = 0;
        nums.forEach((num) => {
          if (num > 0) {
            positiveNumbers++;
          }
        });
        return positiveNumbers;
      }
    </script>
  </body>
</html>
```

# .addEventListener()

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <button onclick="" class="js-button">Click</button>

    <script>
      const buttonElement = document.querySelector(".js-button");

      buttonElement.addEventListener("click", () => {
        console.log("click");
      });
    </script>
  </body>
</html>
```

what is `.addEventListener()` advantages:

1. multiple event listener for one event
2. remove event listener

   `.removeEventListener()`

so we can have more control of the button compare with `onclick`

### .filter() .map()
