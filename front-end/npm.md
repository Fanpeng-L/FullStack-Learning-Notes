# JavaScript package manager (npm) 
Starting around 2010, several JavaScript package managers emerged to help 🦾automate🦾 the process of downloading and upgrading libraries from a central repository. npm has been most popular since around 2015. (around late 2016, yarn picked up a lot of attention)

> npm was originally a package manager made specifically for node.js, a JavaScript runtime designed to run on the server side, not the front end.

## 1. 🔨Use of npm:

`$ npm init`  
This will generate a file named `package.json`:
```json
{  
  "name": "your-project-name",  
  "version": "1.0.0",  
  "description": "",  
  "main": "index.js",  
  "scripts": {  
    "test": "echo \"Error: no test specified\" && exit 1"  
  },  
  "author": "",  
  "license": "ISC"  
}
```

`$ npm install moment --save`  
This command does two things: first, it downloads all the code from the moment.js package into a folder called node_modules. Second, it automatically modifies the package.json file to keep track of moment.js as a project dependency.

```json
{  
  "name": "modern-javascript-example",  
  "version": "1.0.0",  
  "description": "",  
  "main": "index.js",  
  "scripts": {  
    "test": "echo \"Error: no test specified\" && exit 1"  
  },  
  "author": "",  
  "license": "ISC",  
  "dependencies": {  
    "moment": "^2.22.2"  
  } 
}
```
Now, when sharing a project with others — instead of sharing the whole `node_modules` folder, you only need to share the `package.json` file and other developers can install the required packages with the command `npm install`.

## 2. Transpiling code for new language features (babel) 
Transpiling code means converting the code in one language to code in another similar language. Browsers are slow to add new features, so new languages were created with experimental features that transpile to browser-compatible languages.

For CSS, there’s Sass, Less, and Stylus, to name a few. For JavaScript, nowadays most people use **babel** or **TypeScript**. 
