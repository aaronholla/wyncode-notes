# The DOM
Programming interface for HTML and XML. Everything in the dom is part of the document tree. Every element branches from something else all the way up to the main html document.

> Inputs always return a string no matter what type.
## Elements

HTML nodes, or individual branches in the tree.

### selecting one item

```js
let node1 = document.getElementById("intro")
let node2 = querySelector("header h1.title")
```

### selecting multiple items

```js
let nodeList1 = document.querySelectorAll("input");
let nodeList2 = document.getElementsByClassName("classy");
let nodeList3 = document.getElementsByTagName("label");
```

> These methods are plural because your getting a nodelist. `Elements`

## NodeList

An array that contains dom nodes in it. Different from a normal array because it has node for each element. 


## Attributes

something elements have on them to set properties.

```js
let img = document.createElement('img')
// img = document.createElement
img.src = "http://placepuppy.net/200/200"
img.alt = "Puppy"
```

## Create Dom nodes

```js
let img = document.createElement('img')
```

## Connecting Dom nodes

```js
let header = document.createElement("header");
let main = document.getElementById("main-element") 
main.appendChild( header )
```

```js
// direct access to body and head elements. Not a nodelist it is just the elements.
document.body
document.head
```

## Dom Events

The browser has thousands of events that happen and you can listen for these events to happen. Here are some events that happen in the browser:

mouseenter  
mouseleave  
click  
submit  
change  
scroll  
DOMContentLoaded - check if dom is fully loaded ( $.ready() in JQuery)

```js
document.addEventListener('DOMContentLoaded', callBackFunction)
```