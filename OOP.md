Have an object wanna package it up with data
Have data wanna package it into structure

Classes in javaScript are just syntax sugar, there are no classes in javaScript.


get to an object
```js
let obj = {}
```

a class in javaSript is a function
```js
class Foo{

}
console.log(typeof Foo)
// function
```

a new constructor of an class is just an object
```js
class Foo{

}
console.log(typeof new Foo)
// object
```

create a new constructor for your class
```js
class Person{
  constructor(firstName, lastName){
    this.firstName = firstName
    this.lastName = lastName
  }
}

[
  ['Gabriel', 'Smith'],
  ['Nicole', 'Jones'],
  ['Micha', 'Clinton'],
].forEach(([firstName, lastname]) => {
  const person = new Person(firstName, lastName)
  
})
```

The constructor function is called one time when you use the new keyword.