# TypeScript.Basics
This is a basic guide to typescript language syntax.

## **Variable Declaration**

DataTypes in TypeScript
1. number : In typescript there is a singular datatype called 'number' which covers integer and float values
2. string : String type of variable is used to store characters/words/sentences.
3. Boolean : Bool types are used to save binary values such as True or False.

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
```
let Name: string = "Tony"
let age: number = 100
let isHero: boolean = true
```
Here the variable Name can only be assigned a 'String' value, Age a 'number' value, and isHero a 'boolean' value.
A Variable can be assigned multiple datatypes,
```let age: number | string = 100```
Here the variable age can be assigned a number or a string. But I would recommend using single datatyped variables while working on a project. 


