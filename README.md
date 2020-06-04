# TypeScript.Basics
This is a basic guide to typescript language syntax.

## **Variable Declaration**

Declaring Variables using ```let``` keyword
```
let Name = "Banner"
let age = 50
let isGreen = true
```
```let``` Keyword uses *block-scoping*. What that means is variables defined by ```let``` keyword are inaccessable out side of a functional or a conditional block.
For Example:
```
if (condition) {
    // variable a can only be used and referenced in this if block
    let a = 100
}

//console.log cannot output a as it does not exist
console.log(a)
```

Declaring Variables using ```const``` keyword
```
const Name = "Banner"
const age = 50
const isGreen = true
```
Variable declared ```const``` keyword cannot be reassigned or mutated after they are declared.


