# Intro to Javascript

The only programming language that runs in the browser. It is strictly typed, has to be syntaxly correct.

## MATH

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math

All basic math functions are supported in javascript.

```js
2*2
1+1
3-2
6/2
```

Increment `++`  
Decrement `--`  
Addition Assign `+=`  
Subtract Assign `-=`  
Multiply Assign `*=`  
Division Assign `/=`  

Multiply `*`
```js
3 * 2
// 6
```

Exponent `**`
```js
3 ** 2
// 9
```

Modulo `%`
```js
15 % 2
// 1
14 % 2
// 0
```

Random
```js
myArray = [1, 2, 3, 4]
myArray[ Math.floor(Math.random() * myArray.length) ]
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

## Functions

A function is a repeatable set of statements that perform a set of tasks.

You declare the function once and invoke it when you need to run the set of instructions.

You pass in parameters into a funtion that it can use. These are sometimes also called params, args, arguments or input.

```js
function sayHello(recipient) {
    console.log(`Hello ${recipient}!`)
}
```

Once you declare a function you have to call it for it to run.

```js
sayHello("C34")
```

You can give it function params defaults as well.

```js
function sayHello(recipient = "Aaron") {
    console.log(`Hello ${recipient}!`)
}
```

```js
const sayGoodbye = function(recipient) {
    console.log(`Goodbye, ${recipient}, from ${sender}`)
}

sayGoodbye("Aaron")
```

You can pass multiple params.

```js
function sumOf(num1, num2) {
    console.log(num1 + num2)
}

sumOf(13,54)
```

Returning values from function so you can get the value out of the function.

```js
function sumOf(num1, num2){
    return(num1 + num2)
}

const answer1 = sumOf(12, 10)
```

## Spread Operators `ES6`
 Lets you output the values of arrays and shovel them where you need them.

```js

function sumOf(num1, num2) {
    return num1 + num2
}

const nums = [3,4]

const answer = sumOf(...nums)
```

## Rest Parameters `ES6`

Lets you get the rest of params past the ones defined. 

```js
function sumOf(num1, num2, ...rest) {
    let sumOfRest = 0
    for(let i = 0; i < rest.length; i++){
        sumOfRest += rest[i]
    }
    return num1 + num2 + sumOfRest
}

console.log(sumOf(1,2,3,4,5))
```

## Arrow Function Syntax `ES6`

> Function Decloration  
> Function Expression  

There is no function keyword.

```js
const sayHello = (sender, recipient) => {
    console.log(`Hello ${recipient}, from ${sender}`)
}

sayHello("Andy", "C34")
```

if there is only one param the parentacies are optional.

```js
const sayHello = sender => {
    console.log(`Hello ${recipient}!`)
}

sayHello("Andy")
```

You can return the same way as normal function using the return keyword.

```js
const sumOf = (num1, num2) => {
    return num1 + num2
}

const answer = sumOf(3,4)

console.log(answer)
```

Can also return with perentacies instead of curly braces and no keyword needed.

```js
const sumOf = (num1, num2) => (
    num1 + num2
)

const answer = sumOf(3,4)

console.log(answer)
```

If you only have one line in your function you can also put the entire function on a single line.

```js
const sumOf = (num1, num2) => num1 + num2
```


## Loops

Javascript has different types of loops, you can use them in different ways depending on the datatype that you are looping through.

### For Loops

```js
for (let i = 0; i < 5; i++) {
    console.log(i)
}

const dogs = ["boxer", "labs", "poodle"]

for (let i = 0; i < dogs.length; i++) {
    console.log(dogs[i])
}
```

### For In Loops

```js
const teams = {
    'Miami': 'Dolphins',
    'New York': 'Jets',
    'Carolina': 'Panthers'
}

for (location in teams) {
    console.log(`The team from ${location} is the ${teams[location]}`)
}
```

### While Loops
> Don't forget to increment while loops, you will end up in an infinate loop.

```js
let i = 0
while (i < 5) {
    console.log(i)
    i++
}
```

`break` will end your while loop.  
`continue` will go to the next iteration

### Do While Loops
> If condition is false a while loop will not run, use do while loop if value is false. 

```js
// Will not run
while(false){
    console.log("Hello world")
}

// Will run once
do {
    console.log("Hello world")
} while(false)
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

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String

Text value. Can use single quotes or double quotes

 ```js
    let string = "This is a string"
 ```  

#### Escaping

Certian characters need to be escaped to be able to use. Like a double quote inside other double quotes.

> Escaping tells the computer to actually use the character inside the string.

```js
// use a backslash \ to use double quotes inside the other
alert("I said, \"Hey! Let's go outside.\"")

alert('I said, "Hey! Let\'s go outside."')
```

#### Special Characters

There are certian characters you can use in strings to get new lines, tabs, etc.

```js
alert('<section>\n\t<p>I said, "Hey Lets\'s go outside."\n</section>')
/* Output...
<section>
    <p>I said, "Hey Lets\'s go outside.</p>
</section
*/
```

Strings have properties and methods.
- Properties are just accessed by calling the property name on the string.
```js
name.length
```
- Methods are functions.
```js
let greeting = "Welcome to Miami!"
greeting.replace("Miami", "San Francisco")
greeting.toUpperCase()
greeting.charAt(8)
```

#### Comparing Strings

You can check if things are the same using double equals.


```js
let name = "John"
let otherGuy = "Jon"
let newGuy = "John"

name == otherGuy
// false
```

#### String Concatenation

Use the + to build variables into strings. This will mash variable and string into one single string.

```js
console.log("Hello, " + name + ". How are you today?")
```

#### String Interpolation

A way to insert variables into a string template literal.

> Template Literals use backticks instead of quotes.

```js
console.log(`Hello, ${name}. How are you today?`)
```


### Number

Type of numeric values including whole number or decimals numbers

```js
    let number = 50
```

#### Comparing Numbers

`<` less than  
`<=` less than or equal  
`>` greater than  
`>=` greater than or equal  
`==` equality  
`===` strict equality  
`!=` inequality  
`!==` strict inequality  

> You most likely will want to use strict equality and strict inequality in almost all cases. There may be specific instences that you need, but to be safe just use strict.

### Boolean

`true` or `false` values.

> These keywords have no quotes around them. It is just the words them selves

Truthy and falsey values. You an treat certian things as a boolean and they will be considered true or false.

Falsey Examples:  
- 0  
- NaN  
- null  
- false  
- undefined  
- ""  

#### Logical Operators

Ways of checking if multple things are truthy or falsey.

> Place perentacies for order of operations.

`&&` and
> The last truthy or the first falsey item will return if no truthy.

`||` or 
> The first truthy or the last falsey item will return if there are no truthy.

Assigning default values with or operator. If there is no value it will use the last truthy option.

```js
let myVar = undefined
myVar = myVar || 5
// 5
let myOtherVar = 10
myOtherVar = myVar || 15
```

`!` not = Also called Bang 
> Turns a value into a boolean. Single `!` will return oposite boolean value. `!!` is used to return the boolean representation of the variable.

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

## Control Flow

### if/else/else if

```js
let cat = "meow"

if( cat === "meow"){
    console.log("Nice kitty.")
} else {
    console.log("Have you see my cat?")
}

let myName = "Aaron"
let age = 26

if (myName === "Aaron" && age > 30) {
    console.log("Your old")
}


let myNum = Math.random()

if (myNum) > 0.66 {
    console.log("Rock")
} else if (myNum > 0.33) {
    console.log("Paper")
} else {
    console.log("Scissors")
}
```

### Ternary Operators

Shorthand way of writing if/else statements.

```js
let myAge = 30
myAge > 30 ? console.log("old") : console.log("young")
```

### Switch Statements

> Good for if you know the value is going to be just a few different specific values.

```js
let cat = "meow"
switch(cat)
    case "meow":
        console.log("Nice kitty")
        break
    case "ruff":
        console.log("You are a dog!")
        break
    default:
        console.log("Are you really a cat?")
        break
```

## Errors

You can check if there are errors in your code.

### Try Catch

```js
try {
    foo += "bar"
}
catch(error) {
    console.log("Something went wrong")
    console.dir(error)
}
```

## MANIPULATE THE DOM WITH JS
1) Use HTML and CSS to represent the initial state of the page

> Apply just enough styling to get the initial state where we want.

2) Apply ids / classes to any elements that are interactive or dynamic
3) Write CSS that will display any dynamic elements in each of their possible states

> Should be able to edit the classes and have it change to all the different states

Step by step in the console using javascript:

```js
const lightbulb = document.querySelector('#lightbulb');
lightbulb.classList.remove('off');
lightbulb.classList.add('on');

const room = document.querySelector('#room')
room.classList.remove('dark');
room.classList.add('light');
```
4) Write at least one JS function that can add or remove classes from any dynamic elements (or change their textContent or innerHTML)


use `<script></script>` for javascript code in html

```js
function flickTheSwitch() {
    // do something...
}
```

> .toggle = if it doesn't have it will add, if it has it will remove.

5) Add event listeners to run these functions in response to user actions


Elements in javscript listen to different events. you can add these listeners to an element and have it do something when it triggers an event. (form submission, user scroll, select dropdown, window resize)

https://developer.mozilla.org/en-US/docs/Web/Events

```js
// listen for the 'click' event and call the function
lightswitch.addEventListener('click', flickTheSwitch)
```