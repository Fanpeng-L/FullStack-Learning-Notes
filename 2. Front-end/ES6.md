# class

getters and setters:

```js
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
const novel = new Book("anonymous");
console.log(novel.writer);
novel.writer = "newAuthor";
console.log(novel.writer);
```

# import

import all of file’s contents into the current file. use the `import * as` syntax:

```js
import * as stringFunctions from "./string_functions.js";
// stringFunctions can be called anything.

stringFunctions.uppercaseString("hello");
stringFunctions.lowercaseString("WORLD!");
```

Import a Default Export:

```js
import add from "./math_functions.js";
```

only difference is that the default import value `add`, is not surrounded by curly braces (`{}`).

# Create a Promise

When the task completes, you either fulfils your promise or fail to do so. `Promise` is a constructor function, so you need to use the `new` keyword to create one. It takes a function, as its argument, with two parameters - `resolve` and `reject`:

```js
const makeServerRequest = new Promise((resolve, reject) => {
  let responseFromServer;

  if (responseFromServer) {
    // Change this line
    resolve("We got the data");
  } else {
    // Change this line
    reject("Data not received");
  }
});
```

# `then` method

it is executed immediately after the promise is fulfilled with `resolve`:

```js
const makeServerRequest = new Promise((resolve, reject) => {
  let responseFromServer = true;

  if (responseFromServer) {
    resolve("We got the data");
    makeServerRequest.then((result) => {
      console.log(result);
    });
  } else {
    reject("Data not received");
  }
});
```

# Handle a Rejected Promise with `catch`

`catch` is the method used when your promise has been rejected. It is executed immediately after a promise's `reject` method is called:

```js
const makeServerRequest = new Promise((resolve, reject) => {
  // responseFromServer is set to false to represent an unsuccessful response from a server
  let responseFromServer = false;

  if (responseFromServer) {
    resolve("We got the data");
  } else {
    reject("Data not received");
  }
});

makeServerRequest.then((result) => {
  console.log(result);
});

makeServerRequest.catch((error) => {
  console.log(error);
});
```
