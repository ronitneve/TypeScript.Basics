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
Variable declared ```const``` keyword cannot be reassigned or mutated after they are declared. ```const``` keyword also uses the same *block-scoping* method.

By default typescript and javascript can infer the datatype of a variable once it has been assigned a value. But typescript comes with a feature to assign data type to a variable.
```let Name: string = "Tony"``` Here the variable Name can only be assigned a 'String' value.
```
let age: number = 100
let isHero: boolean = true
```
A Variable can be assigned multiple datatypes, ```let age: number | string = 100``` Here the variable age can be assigned a number or a string. But I would recommend using single datatyped variables while working on a project. 


