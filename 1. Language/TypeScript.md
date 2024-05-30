# Dynamic VS. Static Typing

- **Static**: Java, C, C++, Go...
  (_assign type to variables_)

- **Dynamic**: Javascript, Python, Ruby, PHP...

vanilla TS setup:

⭐️ Browsers don't read .ts files, TypeScript need to be compiled with `tsc`.

**`.ts -> Compiler -> .js`**

# TS features

- Type checking
- Code completion
- Refactoring
- Shorthand notation

# basics

```ts
let id: number = 5;
let age: number;
age = 40;
let company: string = "Google Inc";
let isPublished: boolean = false;
let x: any = "hello";

x = true;
```

# array type

```ts
let ids: number[] = [12, 23, 6, 745, 3];

let arr: string[] = ["hi", "hello"];
```

# tuple type

```ts
let person: [number, string] = [1, "Tom"];
```

# enum type

```ts
enum Direction1 {
  Up = 1,
  Down,
  Left,
  Right,
}
console.log(Direction1.Down); // 2

enum Size {
  Small = "s",
  Medium = "m",
  Large = "l",
}
console.log(Size.Medium); //m
```

# object type

```ts
// type alias
type Employee = {
  readonly id: number;
  name: string;
  retire: (date: Date) => void;
};

const employee1: Employee = {
  id: 1,
  name: "John",
  retire: (date: Date) => console.log(date),
};
```

# function type

always annotate types for parameters, return values.

`"noUnusedParameters": true,`
`"noImplicitReturns":true,`
`"noUnusedLocals":true,`

if parameters is not used, can provide default values

```ts
function addNum(x: number, y: number): number {
  return x + y;
}
```

# union type

type1 or type2

```ts
function kgToLbs(weight: number | string): number {
  if (typeof weight === "number") return weight * 2;
  else return parseInt(weight) * 2;
}

kgToLbs(10);
kgToLbs("10kg");
```

# intersection type

type1 and type2

```ts
type Draggable = {
  drag: () => void;
};
type Resizable = {
  resize: () => void;
};

type UIWidget = Draggable & Resizable;

let textbox = UIWidget ={
  drag: () =>void,
  resize: () =>void
}
```

# literal type

annotate with some specific value

```ts
// literal with union:
type Quantity = 50 | 100;
let quantity1 = (Quantity = 100);

type Metric = "cm" | "inch";
let newMetric = (Metric = "cm");
```

# deal with null/undefined

we have to use union type when passing a null or undefined value

```ts
function greet(name: string | null | undefined) {
  if (name) {
    console.log(`hello ${name}`);
  } else {
    console.log("Hello");
  }
}

greet(null);
```

# optional chaining

optional property access operator

```ts
type User = {
  birthday: Date;
};

function getUser(id: number): User | null | undefined {
  return id === 0 ? null : { birthday: new Date() };
}

let user1 = getUser(1);
console.log(user1?.birthday); //check if the user is not null or undefined
```

optional element access operator

optional call access operator

# interface: custom type

```ts
interface Author {
  name: string;
  age: number;
}

const author1: Author = {
  name: "john",
  age: 35,
};

interface Post {
  title: string;
  body: string;
  tags: string[];
  createdAt: Date;
  author: Author; // put the Author interface into this post interface
}

const newPost: Post = {
  title: "my first post",
  body: "something fun",
  tags: ["gaming", "fun"],
  created_at: new Date(),
  author: author1,
};
```

interface as function argument

```ts
function createPost(post: Post): void {
  console.log(post.title);
  console.log(post.author.age);
}
```

# class

```ts
// classes
class Person {
  // there are three modes in the class, private, public and protected. default is public
  id: number;
  name: string;

  constructor(id: number, name: string) {
    this.id = id;
    this.name = name;
  }
}

const lisa = new Person(1, "Lisa");
const mary = new Person(2, "Mary");

// subclass
class Employee extends Person {
  position: string;

  constructor(id: number, name: string, position: string) {
    super(id, name);
    this.position = position;
  }
}

const emp = new Employee(3, "peter", "developer");

// generics, like define a placeholder for the type
function getArray<T>(items: T[]): T[] {
  return new Array().concat(items);
}

let numArray = getArray<number>([1, 2, 3, 4]);
let strArray = getArray<string>(["john", "peter", "lisa"]);
```
