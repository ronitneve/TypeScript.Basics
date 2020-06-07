# TypeScript.Basics
This is a basic guide to typescript language syntax. it's super compact and can get you started right away!

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
```let``` Keyword uses *block-scoping*. What that means is variables defined by ```let``` keyword are inaccessible out side of a functional or a conditional block.
For Example:
```
if (condition) {
    // variable 'a' can only be used and referenced in this 'if' block
    let a = 100
}

//console.log cannot output 'a' as it does not exist outside of the 'if' block.
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

We assign a dynamic datatype by using the keyword ```any```.
```
let Name: any;
Name = 100
Name = "Tony"
//Here by using the any keyword we can assign any type of value to the variable Name.
```

## **Arrays**

Arrays are collection of similar values. all values in an array are indexed with a number. All arrays in TS start with the index 0.
```
let names: string[] = ["Banner", "Tony", "Steve"]
let ages: number[] = [36, 42, 98]
```

We can access array elements, and operate on those elements using it's index. 
```
// This code outputs the first name from the array.
console.log(names[0])

// This code assigns "Steph" to the array "names" at index 0
names[0] = "Steph"

// This code outputs the sum of elements at index 0 and 1.
console.log(ages[0] + ages[1])
```
Arrays have many predefined functions that help us perform various operations on the array elements. Here are few.
* concat() - Returns a new array comprised of this array joined with other array(s) and/or value(s).
* pop() -
Removes the last element from an array and returns that element.
* push() -
Adds one or more elements to the end of an array and returns the new length of the array.
* reverse() - 
Reverses the order of the elements of an array -- the first becomes the last, and the last becomes the first.
* sort() -
Sorts the elements of an array.

We can create an array which stores elements of multiple datatypes.
```
let mixedArray: (string | number)[] = []
mixedArray.push(1)
mixedArray.push("String Text")

console.log(mixedArray)
///output: [ 1, 'String Text' ]
```
## **Tuples**

Tuple types allow you to express an array with a fixed number of elements whose types are known, but need not be the same. Tuples can use array methods. 

```
// Declare a tuple type
let x: [string, number];

// Initialize it
x = ["Tony", 50];
```
Tuple initialization has to follow the same datatypes as the declaraction.
```
//this code will through an error
x = [50, "Tony"]; 
```
We can access the elements of an tuple just like an array using the index.
```
console.log(x[0])
//output: Tony
```

## **Objects**

Object in Typescript is a collection of multiple elements in a 'key = value' pair. Keys are variables that can all have the same or different datatypes.
```
//Example of object Declaration without assignment.
let objectExample: {
    name: string;
    age: number;
};
```
The object heros has 3 elements, 'name', 'age' and 'isHuman' of type 'string', 'number' and 'boolean' respectively.
```
let heros = {
    name: "Tony",
    age: 42,
    isHuman: true,
}
//To Access values
console.log(heros.name)
console.log(heros.age)
console.log(heros.isHuman)
```
Once the object is created we cannot add additional keys to the object, or change the datatype of the values.
```
heros.age = "String Value"
//This assignment will generate an error as the age key is of number type.
heros.isAvenger = true
//This assignment will generate an error as the key isAvenger is not in the initial object creation.
```
We can also create objects that have functions in it.
```
let heros = {
    name: "Tony",
    age: 42,
    isHuman: true,
    isSenior: function () { return this.age > 60; }
};
//output here is false
console.log(heros.isSenior())
```

## **Functions**

 A function is a block of code that can be reused. Insted of rewriting that code multiple times we can just call a function that contains said code.

 Syntax of a Function:
 ```
 function fName(//parameters): //return Type{
     //statements
 }
```

Function paramters can have a fixed datatype and a default value. ```function``` also allows us to have optional parameters.

```
//function add with 2 parameters of type number,
//and this fuction returns a value of type number.
function add(a: number, b: number): number {
    return a + b
}
console.log(add(10, 10))
```
Function Declaration using a default paramter value
```
//Parameter 'c' has a default value of 0.
function add(a: number, b: number, c: number = 0): number {
    return a + b + c
}
//Function call may or may not have 3 parameters and this would work just fine.
add(10, 10)
add(10, 10, 10)
```
Function declaration with a optional paramter.

```
function add(a: number, b: number, c?: number): number {
    //if condition block returns true if 'c' has a value.
    if (c) {
        return a + b + c
    }
    return a + b
}
//Function call may or may not have 3 parameters and this would work just fine.
add(10, 10, 10)
add(10, 10)
```

## **Loops**

**For Loop**

The for loop is used to execute a block of code a given number of times, which is specified by a condition.
Basic syntax goes like this:
```
for (first expression; second expression; third expression ) {
    // statements to be executed repeatedly
}
```

There are three types of for loops:
* for loop
* for..of loop
* for..in loop

Basic for loop:
```
for (let i = 0; i < 3; i++) {
  console.log ("Block statement execution no." + i);
}

output:
Block statement execution no.0
Block statement execution no.1
Block statement execution no.2
```

The for...of loop:
```
let arr = [10, 20, 30, 40];

for (var val of arr) {
  console.log(val); 
}

outputs:
 10, 20, 30, 40
```

The for...in loop:
```
let arr = [10, 20, 30, 40];

for (var index in arr) {
  console.log(index);
}
//for..in loop returns the 'index' of the arr
output:
0, 1, 2, 3
```

**While loop**
The while loop is another type of loop that checks for a specified condition before beginning to execute the block of statements. The loop runs until the condition value is met. Basic syntax goes like this:
```
while (condition expression) {
    // code block to be executed
}
```
It's pretty straight forward, let's look at an example:
```
let i: number = 2;

while (i < 4) {
    console.log( "Block statement execution no." + i )
    i++;
}

output:
Block statement execution no.2
Block statement execution no.3
```

**Do...While loop**

The do..while loop is similar to the while loop, except that the condition is given at the end of the loop. The statements execute at least once in this loop.
Basic syntax goes like this:
```
do {
// code block to be executed
}
while (condition expression);
```

Example:
```
let i: number = 2;
do {
    console.log("Block statement execution no." + i )
    i++;
} while ( i < 4)

output:
Block statement execution no.2
Block statement execution no.3
```
Example with a false condition to see if executes the code at least once.
```
let i: number = 4;
do {
    console.log( "Block statement execution no." + i )
    i++;
} while ( i < 4)

output:
Block statement execution no.4
```

## **Classes**
In the latest version of typescript we can now use typescript with an Object Oriented Approach using classes.
A class is like a blueprint that is used to create an object. Or we can imagine class as 'datatype' which we define, it can have properties or attributes and fucntions that help us operate on a class object.

In following example of Employee class, 'eName' and 'eAge' are attributes and the showEmp() is a Function.
```
class Employee {
    eName: string;
    eAge: number;
    constructor(name: string, age: number) {
        this.eName = name;
        this.eAge = age;
    }

    showEmp() {
        console.log(this.eName);
        console.log(this.eAge);
    }
}

//creating a Employee object
let emp = new Employee('Tony', 42)

//call a Employee class function
emp.showEmp()
//output: Tony 42
```
Inheritance is one of the important concepts of Object Oriented Programming. It's the mechanism of basing an object or class upon another object or class. 

What that means is using inheritance we can create a new class which can inherit attributes and functions of another class. This helps us reuse code and extend previous code with new funcationality.

In the following example, we use the previous Employee class and add a new attribute of Department Name to it. The ``extends`` keyword is used to invoke inheritance. The ```super``` keyword is used to refer to the parent or base class, which in this case is the Employee class.
```
class Department extends Employee {
    dept: string;
    constructor(name: string, age: number, eDept: string) {
        super(name, age);
        this.dept = eDept;
    }

    showDept() {
        super.showEmp()
        console.log(this.dept);

    }
}

let dep = new Department('Tony', 42, 'Avengers')
dep.showDept()
//output: Tony 42 Avengers
```

While creating a class we have a option to set privacy rules to the class elements. This is achived with 'Access Specifier'. There are 3 types of access that we can grant, ```'readonly'```, ```'private'``` and ``` 'public'```.

A ```public``` attribute is accessible to us anywhere in the code, a ```private``` attribute is accessible only inside the class block, and a ```readonly``` attribute is also accessible anywhere in the code but we cannot reassign a new value to it.

 ```
 class Employee {
    private eName: string;
    readonly eAge: number;
    constructor(name: string, age: number) {
        this.eName = name;
        this.eAge = age;
    }

    showEmp() {
        console.log(this.eName);
        console.log(this.eAge);
    }
}

//Create object
let emp = new Employee('Tony', 42)

//This code throws error as eName is private and inaccessible outside the class
console.log(emp.eName)

//this code outputs the eAge attribute as it is accessible.
console.log(emp.eAge)

//this code thows an error as eAge is read only and cannot be reassigned
emp.eAge = 100;
```

## **Interface**

An Interface is a defination of a Structure. It can have attributes and functions just like a class. The difference is that a class is used to create an Object, where as an interface is used to create variables of the type 'interface'. 

What it means is, the variable created using an 'interface'  should have the same properties as the inteface which it is based on. 

To declare an interface we have to use the keyword ```interface```. Let's look at an example.
```
//An interface 'person' is created.
interface person {
    name: string;
    age: number;
    display(): void;
}
```
Any variables created using the 'person' interface has to have the same attributes and implement the same functions as the 'person' interface.

```
//A variable 'firstPerson' is created of type 'person'
let firstPerson: person = {
    name: "Banner",
    age: 40,
    display(): void {
        console.log(this.name)
        console.log(this.age)
    }
}

//to call the function display()
firstPerson.display()
//output: Banner 40
```
We can reassign values of these variables using a simple assignment operator '='. 
```
//A variable 'secondPerson' is created of type 'person'
let secondPerson: person = {
    name: "Tony",
    age: 50,
    display(): void {
        console.log(this.name)
        console.log(this.age)
    }
}

secondPerson.age = 100
secondPerson.display()
//output: Tony 100
```

