# 1. Intro

JS that runs outside of browser.

We can use the `node` REPL to run code.

`global`

# 2. Module

`exports`

# 3. Require

⭐️ the `import` statement is only allowed in ES modules and cannot be used in embedded scripts without the type="module" attribute.

Also, to use ES modules in Node.js, you must save such modules with an extension of `.mjs`:

```js
// utils.mjs
export const getFullName = (firstname, lastName) => {
  return `my fullname is ${firstname} ${lastName}`;
};

// index.js
import { getFullName } from "./utils.mjs";
console.log(getFullName("John", "Doe")); // My fullname is John Doe
```
