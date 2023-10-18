Around 2010, several JavaScript package managers emerged to help 🦾automate🦾 the process of downloading and upgrading libraries from a central repository. npm has been most popular since around 2015. (around late 2016, yarn picked up a lot of attention)

# 💜 Basics

## 1. install

`npm i <package name>` install locally

`npm i -g <package name>` install globally

## 2. `package.json`

`$ npm init`

It will ask a bunch of questions to set up, and then write a package.json file.

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
