# TypeScript Crash Course

# Installation

`yarn add typescript`
You can add globally too.

Commands:
`tsc -v`

Use `.ts` files.
You can start coding with regular js:
`let x = 1;`

# Compilation

`tsc` - compiles all the files it finds.
`tsc index` - compiles a specific file
No need for .ts.

By default, it uses ES5. You can change it to ES6 or any other version.
In `tsconfig.json` change `target` to ES6.

## Watching a file

`tsc --watch index`

## Configuration

`tsc --init`

In the config files you can change the ES standard, the module system, allowing js etc.
Also rootDir, outDir.

# Types

`let x: number = 3;`
If you don't declare the type, ts will do it automatically when you assign the variable.

## ## Types:

- number
- string
- boolean
- any

`any` allows you to use dynamic typing for that variable.

Arrays:

`let ids:number[] = [1, 2, 3]`

## Tuples:

`let person: [number, string, boolean] = [1, "hi", true];`

## Tuple Array:

`let employee: [number, string][];`

```
employee = [
    [1, "Hey"],
    [1, "Hey"],
    [1, "Hey"]
]
```

## Unions:

It can be either:
`let id: string | number = 22`

## Enum:

```
enum Direction {
    Up,
    Down,
    Left,
    Right
}
```

They get numbers assigned, starting from 0.
You can change them like `Up = 1`, that changes the following numbers too.
Or set them up with strings `Up = "Up"`

## Objects

```
const user:{
    id: number,
    name: string
} = {
    id: 1,
    name: "John"
}
```

There's another notation:

```
type Useer = {
    id: number,
    name: string
}

const user: User = {
    id: 1,
    name: "John"
}
```

## Type Assertion

Telling the compiler you want to treat an entity as a different type.
Example:

```
let id: any = 1;
let customerID = <number>id

// or

let cusomerID = id as number;
```

## Functions

The default type is `any`.

```
function addNum (x: number, y: number): number {
    return x + y;
}
```

If there's no return value, you can `use: void`

## Interfaces

```
interface UserInterface {
    id: number,
    name: string
}

const user: UserInterface = {
    id: 1,
    name: "Jake"
}
```

## Optional variables

`age? : number`

## Read-Only properties

`readonly id: string`

## Function interfaces

```
interface MathFunc {
    (x: number, y:number): number
}


const add: MathFunc = (x: number, y: number): number => x + y
```

## Classes

```js
class Person {
  id: number;
  name: string;

  constructor(id: number, name: string) {
    this.id = id;
    this.name = name;
  }
}

const John = new Person(55, "John");
```

## Data Modifiers

```js
class Person {
    private id: number
    protected x: number
    public z: number
}
```

## Implementing interface in class

```ts
interface PersonInterface {
  id: number;
  name: string;

  register(): string;
}

class Person implements PersonInterface {
  id: number;
  name: string;

  register() {
    return "String";
  }
}
```

## Extending a class / Subclasses

```ts
class Person implements PersonInterface {
  id: number;
  name: string;

  register() {
    return "String";
  }
}

class Employee extends Person {
  position: string;

  constructor(id: number, name: string, position: string) {
    super(id, name);
    this.position = position;
  }
}
```

# Generics

```ts
function getArray<T>(items: T[]): T[] {
  return new Array().concat(items);
}

let numArray = getArray<number>([1, 2, 3, 4]);
let strArray = getArray<string>(["this", "that", "something else"]);
```

# Adding TS to React

Rename files to .ts or .tsx
No need to use propTypes

```ts
export interface Props {
  title: string;
  color?: string;
}

const Header = (props: Props) => {
  return (
    <header>
      <h1 style{{color: props.color ? props.color : "blue"}}>{props.title}</h1>
    </header>
  );
};

export default Header;
```
