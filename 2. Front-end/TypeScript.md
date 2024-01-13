# Dynamic VS. Static Typing

- **Static**: Java, C, C++, Go...
  (_assign type to variables_)

- Dynamic: Javascript, Python, Ruby, PHP...

vanilla ts setup:

⭐️ Browsers don't read .ts files, TypeScript need to be compiled with `tsc`.

- `tsc --init` the, we can change the target compile version to `es6` in the `tsconfig.json`.

<br>

# TypeScript basics:

```ts
let id: number = 5;
let age: number;
age = 40;
let company: string = "Google Inc";
let isPublished: boolean = false;
let x: any = "hello";

x = true;

let ids: number[] = [12, 23, 6, 745, 3];
ids.push(12);

let arr: any[] = [1, 34, true, "hello"];

//tuple:
let person: [number, string, boolean] = [1, "happy", true];

//tuple array:
let employee: [number, string][];
employee = [
  [1, "mary"],
  [2, "lisa"],
];

//union
let product: string | number = 22;
product = "cake";

//enum
enum Direction1 {
  Up = 1,
  Down,
  Left,
  Right,
}
console.log(Direction1.Up); // 1

enum Direction2 {
  Up = "Up",
  Down = "Down",
  Left = "Left",
  Right = "Right",
}
console.log(Direction1.Left); // Left

//Objects
type User = {
  id: number;
  name: string;
};

const user: User = {
  id: 1,
  name: "John",
};

// type assertion
let cid: any = 1;
// let customerId = <number>cid;
let customerId = cid as number;

//functions
function addNum(x: number, y: number): number {
  return x + y;
}
console.log(addNum(1, 2));

function log(message: string | number): void {
  console.log(message);
}

//interface: custom type
interface userInterface {
  id: number;
  readonly name: string;
  age?: number; // optional
}

const user1: userInterface = {
  id: 1,
  name: "john",
};

//Cannot reassign to 'name' because it is a read-only in the interface
user1.name = "lisa";

// interface with function
interface MathFun {
  (x: number, y: number): number;
}

const add: MathFun = (x: number, y: number): number => x + y;

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
