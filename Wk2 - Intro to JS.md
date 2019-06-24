# Intro to Javascript

The only programming language that runs in the browser. It is strictly typed, has to be syntaxly correct.

## Math

All basic math functions are supported in javascript.

```js
2*2
1+1
3-2
6/2
```

## Variables

- use a name that convays what it is used for.

- Use camelCase as a convention for variable and function names. 

- no spaces
- cant start with numbers, but can have numbers in it

`let` keyword is used to define a variable.  
`const` keyword is used to store a variable that will not change.  

```js
let message = "Hello World"
```

You can create variables with no value.

```js
let message
```

### Reassigning Varaibles

If you did not use `const` you can reassign a variable. 

```js
let message = "Hello World"
message = "This is a new message"
```

> Do not use the `let` keyword when reassinging. If you do it will try to create a new variable with the same name (which will give you an error).

> In older ES5 code the `var` keyword is used. `var` lets you define new variables that will overwrite if existing already. This can cause code to not throw errors.


## Data Types

Javascript has 7 data types. Data types are how you classify different types of data.

Can use the typeof operator to find the datatype.

```js
typeof(2)
// "number"
typeof("test")
// "string"
typeof( [1, 2, 3])
// "object"
typeof(null)
// "object"
```

### String

Text value. Can use single quotes or double quotes

 ```js
    let string = "This is a string"
 ```  

### Number

Type of numeric values including whole number or decimals numbers

```js
    let number = 50
```

### Boolean

True or False values.

> These keywords have no quotes around them. It is just the words them selves

### Null

Null means nothing, it is a object type

### Undefined
Means it has no value

### Object 

Objects are complex datatypes. There are different types of objects.  

- Arrays - holds values in numerically indexed positions. index numbers start at 0.  
- Objects - key value pairs. You can nest Objects inside of each other.

```js
    let teams = { NewYork: "Giants", Miami: "Dolphins" }
    teams
    // { NewYork: "Giants", Miami: "Dolphins" }
    teams.Miami
    // "Dolphins"
```

### Symbol
An identifier that will be unique to identify objects. (what the computer uses to identify for system memory)

## Coercion
> Conversion of one data type to another data typ explicit and implicit.

### Explicit Coercion
Intentional and obvious

let twelve = "12"
Number(twelve)

### Implicit Coercion
When javascript will change a datatype just to get a result for you.

```js
5 + "2"
// "52"
5 - "2"
// 10
```

## Immutable Data Types
 - string 
 - number 
 - bool 
 - undefined 
 - null 
 - symbol
Do not effect the original stored variable.
```js
let myString = "Something"
myString + "Else"

// myString = Something

```
> If you want to update the value of a immutable varaible you have to reassign.

## Mutable Data Types
- objects 
Literal Objects, Arrays, and Functions are all objects so they can be mutated. 

Let you change the original variable without reasignment. Even if they are using `const`. `const` just cant be reassigned.

## Value-copy assignment

If you set a varaible equal to another it will copy the value into it. It does not link them together. If you change one it will not affect the other. It is just taking a snapshow at that assignment point.

## Reference Assignment

When storing object data types in a variable they do not store the value. It is just a reference to the object.

## MANIPULATE THE DOM WITH JS
1) Use HTML and CSS to represent the initial state of the page

> Apply just enough styling to get the initial state where we want.

2) Apply ids / classes to any elements that are interactive or dynamic
3) Write CSS that will display any dynamic elements in each of their possible states

> Should be able to edit the classes and have it change to all the different states

Step by step in the console using javascript:

```js
const lightbulb = document.querySelector('#lightbulb')
lightbulb.classList.remove('off');
lightbulb.classList.add('on');

const room = document.querySelector('#room')
room.classList.remove('dark');
room.classList.add('light');
```
4) Write at least one JS function that can add or remove classes from any dynamic elements (or change their textContent or innerHTML)


use `<script></script>` for javascript code in html

```js
function flickTheSwitch
```

> .toggle = if it doesn't have it will add, if it has it will remove.

5) Add event listeners to run these functions in response to user actions


Elements in javscript listen to different events. you can add these listeners to an element and have it do something when it triggers an event. (form submission, user scroll, select dropdown, window resize)

https://developer.mozilla.org/en-US/docs/Web/Events

```js
// listen for the 'click' event and call the function
lightswitch.addEventListener('click', flickTheSwitch)
```