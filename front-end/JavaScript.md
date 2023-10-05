# 1. Numbers & Math

```js
Math.round(2.2)
//2
Math.round(2.8)
//3
```

# 2. String
```js
`hello`   //backtick string (it can interpolation)  
"hello"
```

# 3. Variables
3 ways to create variable:  
```js
let variable1 = 2;
const variable2 = 3;   // cannot change the value later
var variable3 = 3;     // we don't use it in new javascript code
console.log(typeof vairable2);
```  

# 4. boolean & if
```js
if (true) {
console.log('hello');
} else {
console.log('bye');
}

&&     //and  
||     //or  
!true  //not 
```

☆ `if` statement create **new scope**. the variable created within the scope cannot be accessed outside of the scope.

`? : ` (ternary operator)
```js
if (true) {'truthy'}
else {'falsy'}
// 👆this is equal to this👇
const result = true ? 'truthy' : 'falsy';
console.log(result);  //truthy
const result = 0 ? 'truthy' : 'falsy';
console.log(result);  //falsy
```

`&&` (guard operator):

```jsx
const message = false && 'hello';
console.log(message);
//The code will not run because the left is false

// 👆this is equal to this👇
if (condition) {console.log('hello');}
```

`||` (OR operator, also called default operator)

```jsx
const currency = 'EUR' || 'USD'; 
console.log(currency);    // EUR    because the left side is true. it doesn't run the right side.
const currency = undefined || 'USD'; 
console.log(currency);    // USD    this time it will run the right side.
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
      function calculatorTax(cost, taxPercent=0.1) {
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
      console.log(product["name"]);   //bracket notation. does the same thing as dot.

      product.name = "cotton socks"; //change the value to a new one
      console.log(product);

      product.newProperty = ture;
      console.log(product);

      delete product.newProperty;
      console.log(product);
    </script>

// {name: 'socks', price:1090}
// socks
// {name: 'cotton socks', price:1090}
// {name: 'cotton socks', price:1090, newProperty: true}
// {name: 'cotton socks', price:1090}
```

Nested object:
```html
    <script>
      const product = {
        name: "socks",
        rating: {
	    stars: 4.5,
	    count: 87
	}
      };
      console.log(product.rating.count)

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
```html
const receiveJSON = JSON.parse(sendJSON);
console.log(receiveJSON);
//{name: "Fanpeng", hobbies: Array(3)}
console.log(reveiveJSON);
//object
```

## Local storage  (a little confusing)

all variables are temporary, when refreshing the page, the storage will lost.

Local storage will not clear the variables when refreshing, but **it only support strings:**

```html
localStorage.getItem('message');

localStorage.setItem('message', 'hello'); //save in local storage

localStorage.removeItem('message'); 
```

## Null & undefined

![Screenshot 2023-06-04 at 11.42.03.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/44ed403d-45d3-4350-8927-60acd46f1f54/Screenshot_2023-06-04_at_11.42.03.png)

## Auto-boxing

```html
console.log('hello'.length);
console.log('hello'.toUpperCase());

//JS automatically wrap strings into a special object
```

## Objects are references

working with object, even we create the object with `const`, we can still change the value inside of the object.

when comparing 2 objects, we are comparing the references not the values inside.

### Shortcut:

**destructuring**: take the message property outside the object and save it as a message variable

`const { message } = object;`

👆=👇

`const message = object.message;`

**Shorthand property:**

`const object = { message: message}`

👆=👇

`const object = {message}`

**Shorthand method**

```html
const ojbect = {
	method: funtion function1() {
		console.log("method");
	}
}

👆=👇

const ojbect = {
	method() {
		console.log("method");
	}
}
```

# 8. DOM (built-in document object model)

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

![Screenshot 2023-06-05 at 17.00.00.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e3434737-251b-4d5e-b29f-8141d4283fbd/Screenshot_2023-06-05_at_17.00.00.png)

![Screenshot 2023-06-05 at 17.01.14.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a2427d02-0f39-4787-a59a-f3bedc325fc3/Screenshot_2023-06-05_at_17.01.14.png)

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
    <button onclick="subscribe();" class="js-subscribe-button">Subscribe</button>

    <p>Amazon Shipping Calculator</p>

    <input
      placeholder="Cost of order"
      class="js-cost-input"
      onkeydown="handleCostKeydown(event)" />

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
      " />

    <button
      onclick="
      const inputElement = document.querySelector('.js-name-input');
      document.querySelector('.js-message')
        .innerHTML = `Your name is: ${inputElement.value}`;
    ">
      Submit
    </button>

    <p class="js-message"></p>
  </body>
</html>
```

**window (built-in object) ——the webpage**

```html
window.console
window.document
window.alert
```

# 9. HTML CSS and JS together

```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM Projects</title>
    <style>
      body {
        font-family: Arial, Helvetica, sans-serif;
      }

      .subscribe-button {
        border: none;
        background-color: black;
        color: white;
        padding-top: 10px;
        padding-left: 15px;
        padding-bottom: 10px;
        padding-right: 15px;
        font-weight: bold;
        border-radius: 50px;
        cursor: pointer;
        margin-bottom: 30px;
      }

      .is-subscribed {
        background-color: rgb(240, 240, 240);
        color: black;
      }

      .cost-input {
        font-size: 15px;
        padding: 10px;
      }

      .calculate-button {
        background-color: green;
        color: white;
        border: none;
        font-size: 15px;
        padding: 12px 15px;
        border-radius: 4px;
        cursor: pointer;
      }
    </style>
  </head>

  <body>
    <p>YouTube Subscribe Button</p>

    <button
      onclick="
      subscribe();
    "
      class="js-subscribe-button subscribe-button">
      Subscribe
    </button>

    <p>Amazon Shipping Calculator</p>

    <input
      placeholder="Cost of order"
      class="js-cost-input cost-input"
      onkeydown="
      handleCostKeydown(event);
    " />

    <button
      onclick="
      calculateTotal();
    "
      class="calculate-button">
      Calculate
    </button>

    <p class="js-total-cost"></p>

    <script>
      String(25);
      console.log("25" - 5);
      console.log("25" + 5);

      window.document;
      window.console.log("window");
      window.alert;

      function handleCostKeydown(event) {
        if (event.key === "Enter") {
          calculateTotal();
        }
      }

      function calculateTotal() {
        const inputElement = document.querySelector(".js-cost-input");
        let cost = Number(inputElement.value);

        if (cost < 40) {
          cost = cost + 10;
        }

        document.querySelector(".js-total-cost").innerHTML = `$${cost}`;
      }

      function subscribe() {
        const buttonElement = document.querySelector(".js-subscribe-button");

        if (buttonElement.innerText === "Subscribe") {
          buttonElement.innerHTML = "Subscribed";
          buttonElement.classList.add("is-subscribed");
        } else {
          buttonElement.innerHTML = "Subscribe";
          // add a class to change the color of the button
          buttonElement.classList.remove("is-subscribed");
        }
      }
    </script>
  </body>
</html>
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

```jsx
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
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
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
  </body>
</html>
```

![Screenshot 2023-06-10 at 11.16.56.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b015eafd-1d5e-44eb-a216-eec659bf4c29/Screenshot_2023-06-10_at_11.16.56.png)

array is reference, so array1 and array2 are both modified👆

so, if we don’t want to change the original array, we can make a copy of array1 using `.slice()` method:

![Screenshot 2023-06-10 at 11.40.55.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ac26b79c-6e20-4cf5-982a-52189f42c63e/Screenshot_2023-06-10_at_11.40.55.png)

```html
//other ways to get the value from the array:

const [firstValue, secondValue] = [1,2,3];
```

```jsx
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

# 11. Advanced Functions

### **functions are values**

**they** **can be saved in variables.**

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
      const add = function () {
        console.log(2 + 3);
      };

      add();
    </script>
  </body>
</html>
```

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
      function greeting() {
        console.log("hello");
      }
      greeting();

      const function1 = function greeting() {
        console.log("hello2");
      };

      console.log(function1);
    </script>
  </body>
</html>
```

we can also save the functions value in an object: 

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
      const object1 = {
        num: 2,
        function1: function() {  //here we create an anonymous function within an object
          console.log("hello");
        },
      };
      object1.function1();
    </script>
  </body>
</html>
```

passing a function into another function:

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
      function run(param) {
        param();
      }

      run(function () {
        console.log("hello!");
      });
    </script>
  </body>
</html>
```

### setTimeout() setInterval()

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

![Screenshot 2023-06-10 at 17.18.08.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b9d77e01-d953-4ea7-8826-0744a1f5c7ab/Screenshot_2023-06-10_at_17.18.08.png)

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

### Arrow function

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

### .forEach()

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

### .addEventListener()

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

### .filter()  .map()

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
      [1, -3, 5].filter((value, index) => {
        return value >= 0;
      });

      [1, 1, 3].map((value, index) => {
        return value + 10;
      });

			//👆 is equal to 👇:
			[1, 1, 3].map((value) => value + 10);
    </script>
  </body>
</html>
```

`closure` feature: 

![Screenshot 2023-06-11 at 18.05.04.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4f5a941a-2662-40de-b041-dc9b2c48b3e4/Screenshot_2023-06-11_at_18.05.04.png)

---

# Amazon project

## main idea of JS (3 steps)

1. save the data

often, we use the combination of `list` and `object` to create and save the data of the products

```jsx
const products = [
  {
    image: "images/products/athletic-cotton-socks-6-pairs.jpg",
    name: "Black and Gray Athletic Cotton Socks - 6 Pairs",
    rating: { stars: 4.5, count: 87 },
    priceCents: 1090,
  },

  {
    image: "images/products/intermediate-composite-basketball.jpg",
    name: "Intermediate Size Basketball",
    rating: { stars: 4, count: 127 },
    priceCents: 2095,
  },

  {
    image: "images/products/adults-plain-cotton-tshirt-2-pack-teal.jpg",
    name: "Adults Plain Cotton T-Shirt - 2 Pack",
    rating: { stars: 4.5, count: 56 },
    priceCents: 799,
  },
];
```

1. generate HTML using JS

```jsx
let productsHTML = "";

products.forEach((product) => {
  productsHTML += `
    <div class="product-container">
    <div class="product-image-container">
        <img
        class="product-image"
        src="${product.image}" />
    </div>

    <div class="product-name limit-text-to-2-lines">
        ${product.name}
    </div>

    <div class="product-rating-container">
        <img class="product-rating-stars" src="images/ratings/rating-${
          product.rating.stars * 10
        }.png" />
        <div class="product-rating-count link-primary">${product.rating.count}</div>
    </div>

    <div class="product-price">$${(product.priceCents / 100).toFixed(2)}</div>

    <div class="product-quantity-container">
        <select>
        <option selected value="1">1</option>
        <option value="2">2</option>
        <option value="3">3</option>
        <option value="4">4</option>
        <option value="5">5</option>
        <option value="6">6</option>
        <option value="7">7</option>
        <option value="8">8</option>
        <option value="9">9</option>
        <option value="10">10</option>
        </select>
    </div>

    <div class="product-spacer"></div>

    <div class="added-to-cart">
        <img src="images/icons/checkmark.png" />
        Added
    </div>

    <button class="add-to-cart-button button-primary">Add to Cart</button>
    </div>`;
});

console.log(productsHTML);

document.querySelector(".js-products-grid").innerHTML = productsHTML;
```

the benefits of creating HTML is that we don’t need to copy and paste HTML every time when adding new products, we can simply add in the product list. 

1. make it interactive
