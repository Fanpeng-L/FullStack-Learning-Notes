# 1. Use ****Arrow Functions to Write Anonymous Functions****

- In JS, we often don't need to name our functions, especially when passing a function as an argument to another function. Instead, we create inline functions because we do not reuse them anywhere else:

```tsx
const myFunc = function() {
  const myVar = "value";
  return myVar;
}
```

VS.

```tsx
const myFunc = () => {
  const myVar = "value";
  return myVar;
}
```

- When there is no function body, and only a return value, arrow function can omit `return` as well as the brackets:

```jsx
const myFunc = () => "value";
```

- passing parameters:

```jsx
const multiplier = (item, multi) => item * multi;

multiplier(4, 2);
```

- If an arrow function has a single parameter, the parentheses enclosing the parameter may be omitted:

```jsx
const doubler = item => item * 2;

doubler(4);
```

- ****Set Default Parameters for Your Functions:****

```jsx
const greeting = (name = "Anonymous") => "Hello " + name;

console.log(greeting("John")); // Hello John
console.log(greeting()); // Hello Anonymous
```

# 2. ****Rest Parameter****

```jsx
function howMany(...args) {
  return "You have passed " + args.length + " arguments.";
}

console.log(howMany(0, 1, 2)); //You have passed 3 arguments.
console.log(howMany("string", null, [1, 2, 3], { })); //You have passed 4 arguments.
```

# 3. spread operator

can be used to copy sth. 

it only works in-place, like in an argument to a function:

```jsx
const arr = [6, 89, 3, 45];
const maximus = Math.max(...arr);

//evaluate the max value of the array
```

or in an array literal:

```jsx
const spreaded = [...arr];
```

# 4. ****Destructuring****

for neatly assigning values taken directly from an object:

```jsx
const user = { name: 'John Doe', age: 34 };

const name = user.name;
const age = user.age;
```

can be rewrite to👉: 

```jsx
const { name, age } = user;
```

- **we can also give new variable names in the assignment:**

```jsx
const user = { name: 'John Doe', age: 34 };

const { name: userName, age: userAge } = user;
```

Now, the value of `userName` would be `"John Doe"`, and the value of `userAge` would be `34`.

- ****Assign Variables from Nested Objects:****

```jsx
const user = {
  johnDoe: {
    age: 34,
    email: 'johnDoe@freeCodeCamp.com'
  }
};
```

extract the values of object:

```jsx
const { johnDoe: { age, email }} = user;

```

assign an object properties' values to variables with different names:

```jsx
const { johnDoe: { age: userAge, email: userEmail }} = user;
```

- ****Assign Variables from Arrays:****

```jsx
const [a, b] = [1, 2, 3, 4, 5, 6];

console.log(a, b); // 1, 2
```

- We can also access the value at any index in an array by using commas:

```jsx
const [a, b,,, c] = [1, 2, 3, 4, 5, 6];

console.log(a, b, c); // 1, 2, 5
```

```jsx
//exchange the value: 

let a = 8, b = 6;

[a, b] = [b, a]
```

- collect the `rest` of the elements into a separate array. It is similar to `Array.prototype.slice()`:

```jsx
const [a, b, ...arr] = [1, 2, 3, 4, 5, 7];

console.log(a, b); // 1, 2
console.log(arr); // [3, 4, 5, 7]
```

- **destructure the object in a function argument itself:**

```jsx
const stats = {
  max: 56.78,
  standard_deviation: 4.34,
  median: 34.54,
  mode: 23.87,
  min: -0.75,
  average: 35.85
};

const half = ({max, min}) => (max + min) / 2.0; 
```

# 6. ****Object Property Shorthand****

```jsx
const getMousePosition = (x, y) => ({
  x: x,
  y: y
});
```

is same as:

```jsx
const getMousePosition = (x, y) => ({ x, y });
```

# 7. class

- ****getters and setters:****

```jsx
class Book {
  constructor(author) {
    this._author = author;
  }
  // getter
  get writer() {
    return this._author;
  }
  // setter
  set writer(updatedAuthor) {
    this._author = updatedAuthor;
  }
}
const novel = new Book('anonymous');
console.log(novel.writer);
novel.writer = 'newAuthor';
console.log(novel.writer);
```

# 8. import

import all of file’s contents into the current file. use the `import * as` syntax:

```jsx
import * as stringFunctions from "./string_functions.js"
// stringFunctions can be called anything.

stringFunctions.uppercaseString("hello");
stringFunctions.lowercaseString("WORLD!");
```

- **Import a Default Export:**

```jsx
import add from "./math_functions.js";
```

only difference is that the default import value `add`, is not surrounded by curly braces (`{}`). 

# 9. **Create a Promise**

When the task completes, you either fulfils your promise or fail to do so. `Promise` is a constructor function, so you need to use the `new` keyword to create one. It takes a function, as its argument, with two parameters - `resolve` and `reject`:

```jsx
const makeServerRequest = new Promise((resolve, reject) => {
  let responseFromServer;
    
  if(responseFromServer) {
    // Change this line
    resolve("We got the data")
  } else {  
    // Change this line
    reject("Data not received")
  }
});
```

# 10. The `then` method

it is executed immediately after the promise is fulfilled with `resolve`:

```jsx
const makeServerRequest = new Promise((resolve, reject) => {
  let responseFromServer = true;
    
  if(responseFromServer) {
    resolve("We got the data");
    makeServerRequest.then(result =>{console.log(result)})
  } else {  
    reject("Data not received");
  }
});
```

# 11. ****Handle a Rejected Promise with `catch`**

`catch` is the method used when your promise has been rejected. It is executed immediately after a promise's `reject` method is called:

```jsx
const makeServerRequest = new Promise((resolve, reject) => {
  // responseFromServer is set to false to represent an unsuccessful response from a server
  let responseFromServer = false;
    
  if(responseFromServer) {
    resolve("We got the data");
  } else {  
    reject("Data not received");
  }

});

makeServerRequest.then(result => {
  console.log(result);
});

makeServerRequest.catch(error => {console.log(error)})
```
