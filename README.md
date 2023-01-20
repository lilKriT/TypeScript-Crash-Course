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
