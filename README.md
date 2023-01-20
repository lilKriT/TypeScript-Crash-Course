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
