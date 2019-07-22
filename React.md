# React

ReactDOM.render takes two arguments. What do you want on the page and where do you want it on the page.

```js
ReactDOM.render(<h1>Hello, world!</h1>, document.querySelector('#root'))
```

The first argument above is actually JSX and not a string. Babel will transpile the jsx into html.

# React Components

React Components are just JavaScript functions. When JSX renders the tag it will call your component.

Extend the react.component class to create a new component. Must have a render method and that render method must return JSX.

```js
class Box extends React.Component {
    render(){
        return(
            <h1>Hello from the Box Component</h1>
        )
    }
}

ReactDOM.render(<Box/>, document.querySelector('#root'))
```

> React expects component names to start with a capital. It will not render unless your component name starts with a capital letter.

# Functional Components

Mostly used to break up larger components into smaller pieces. Used to not be able to use state in functional components. But now in react 16.8 you can use hooks to access state and lifecycle methods (effects). 

A function that returns some JSX.

```js
const TodoItem = (props) => {
    return(
        <div>{props.text}</div>
    )
}
```

# Smart Container dumb component pattern

> Always better to build a large number of small things than small number of large things.

All of your state would be inside the container component and each of the dumb components would be able to change the state on a need to know basis.

You can pass functions defined in the parent as props to the child components and call them from inside the child. 

# Methods

Regular functions are built in to react components. Your custom methods should be arrow functions.

# Lifecycle Methods

https://reactjs.org/docs/react-component.html

## ComponentDidMount

> Anything you do in componentdidmount you should undo in componentWillUnmount

It runs before the components render method gets called. Useful for when you wan to do things before the component gets initialized.

```js
class Box extends React.Component {
    state = {
        width: window.innerWidth,
        height: window.innerHeight
    }
    // custom method
    measure = () => {
        const width = window.innerWidth
        const height = window.innerHeight
    }
    // Built in method of React.Component
    componentDidMount() {
        window.addEventListener('resize', this.measure)
    }

    render(){
        const {width, height} = this.state
        return(
            <h1>The Screen Height is {height} and width {width}</h1>
        )
    }
}
```

# State

State in react components is immutable. When using setState it will replace the entire state with the new object.

> You always want the default state to match the datatype that it will ultimately be replaced with.

```js
class StateDataType extends React.Component {
    state = {
        tasks: []
    }
}
```

# Props

Dynamic way of passing in arguments to your react components. Similar to passing in arguments to a function.

# JSX

JSX has ways to escape out of the html/reactComponents and put javascript code. Use the `{}` anything inside of the curly braces will exucute as javascript.

> JSX removes whitespaces.

Inputs are self closing tags in React.

Jsx just calls functions under the hood. It will pass the props in as arguments to the underlying function.

```js
const element = React.createElement(
    'h1',
    {className: 'greeting'},
    'Hello, world!'
)

class Element extends React.Component {
    render(){
        return(
            <h1 className="greeting">Hello, world!</h1>
        )
    }  
}
```