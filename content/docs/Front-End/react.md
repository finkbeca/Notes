---
title: React
weight: 2
bookToc: true
---

# React
---

## Notes

Notes were from the Ebook [React Express](https://www.react.express/)
### Environment
 Two common ways to start Create-react-app and a javascript bundler like webpack.
 Create-react-app is the more common pathway for beginning. Both use npm and node.js

 A javascript bundler combined all your javascript sources files into a single file you can then attach in the scripts of a html page. Webpack is one such example of a bundler.

 ```
 npx create-react-app 
 ```

 ### JSX
 An extension of javascript. JSX is used to create React elements
 Concise for calling API calls

 Each JSX expression has a tag ``` <Example /> ``` which is then called to ``` React.createElement("div") ``` In this case Example is the type of element.  
 Any JSX attributes become props of the react element for example ```<Example name="Colin" Age={20}/> ```  
 Any Children should in between the tag. If no children you can use the shorthand as seen above.  Children could be both other elements, text, or expression in braces.

 React Simply lets us define our UI of our App as a tree of JS Objects. These objects are known as react objects. 

 ### Elements
  Example:
  ```
  const myElement = {
      <div foo="bar">
        <button>Test</button>
        <span>Hello</span>
      </div>
  } 
   ```
  
  A react element most simply is a javascript object containing a type and a props object
  ### Rendering
  In order to see React elements on the screen we must use a rendering library
  We use React DOM library for rendering React elements in browser.
  TO use ReactDOM we must install ``` react-dom ``` from ```npm```. Then 
  ``` import {render} from 'react-dom' ``` we can then render with
  ```render(element, node) ```
 ### Components
 React Components are the reusable blocks of our ui. They are a templates of sorts that takes paramters as inputs and output a react element tree

2 Ways to define a react component  
 1. Functional components: A function that takes paramters (props) as input and returns an react element
 2. A class that extends React.Component and implements a render method

 ``` 
 function MyComponent(props) {
     return (
         <div>
            <button>{props.text}</button>
         </div>
     )
 }

 const Myelement = <Mycomponent text="Hello"/>
 render(Myelement, document.querySelector('#app'))
 ```

The functions instantiaties a div component as a react element who has one child a button element. We then call render to render this hierarchy to the DOM

React.Components allows us to extends from React.Component with our own subclasses and allows for us to override the render method.
Note: this was the original API and can become much more complex for many cases it is better to use functional componants.
```
class MyComponent extends React.Component {
  render() {
    return (
      <div style={{ padding: '30px', backgroundColor: 'lightblue' }}>
        <button>{this.props.text}</button>
      </div>
    )
  }
}

const myElement = <MyComponent text="Hello, world!" />

render(myElement, document.querySelector('#app'))

```

### Styling
There are many different ways to style react components

All react components that render DOM elements accept a style prop which sets the style attribute of a DOM

```<Div style = {{padding: '20px, color: 'white'}}>{children}</div>```

Another option is CSS and Classnames
This is nice as it allows for the full power of CSS and is straightforward, however it is hard with large codebases, the components are not self-contained in a single js file and it works for DOM renderer only (No Native).

Lastly there is CSS-in-JS allowing us to have the benefits of inline and css. It can be used with the CSS-in-JS library
```import styled from 'styled-components' ```
Example:

```

const Card = styled.div`
  padding: 20px;
  text-align: center;
  color: white;
  background-color: ${props => props.color};
`

const Container = styled.div`
  padding: 20px;
`

function App() {
  const [color, setColor] = useState('skyblue')

  return (
    <Container>
      <Card color={color}>
        <input
          type={'button'}
          value={'Randomize Color'}
          onClick={() => setColor(randomColor())}
        />
      </Card>
    </Container>
  )
}
```

Some benefits of this is that it is dynamic, it works on both native and web, styles live in the same file as code, familiar css syntax. However this does rely on a component per style as well as generally increased code size

### Events
DOM nodes w/ React fire events the same as in vanilla Javascript

To add an event handler pass a function as a prop to a React element
```
<input
    onChange = { e => {
        console.log(e)
    }}>
</input>
```

Events in React are camelCase and a list of supported events can be found [here](https://reactjs.org/community/support.html)  

Example 
```
function App() {
  const [count, setCount] = useState[0]

  return (
      <button
      onClick={ () => {
          setCount(count + 1)
      }}> Increment {count} </button>
  )
}

render(<App> document.querySelector('#app'))
```
### User Input

Traditionally user input is stored in the DOM and the data is extracted from the DOM to use in application logic. React simply is this process by treating input components as stateless, an input element has a value prop and onChange prop giving us complete control over the input.

```
function TextInput() {

    const [state, setstate] = useState('')

    return (
        <div>
        <input
        type={'text'}
        value={state}
        onChange={event => {
            setState(event.target.value)
        }}
        />
        You entered {state}
        </div>
    )
}
render(<TextInput/>, document.querySelector('#app'))
```
### Conditional Rendering
A component may return different elements based on props.  A render function just must return a React node, this could be an element, a string, null, or array of these

For simple conditional we can take advantage of ``` && ``` which will return if the firm item is false. Otherwise the expression evaluates to whatever the right hand side is. Note when a prop is not passed in it is undefined. For example give the prop ``` sold ``` we can have conditions like ``` {sold && <h2>{sold}</h2>} ``` this will only cause the H2 to appear when this prop is defined.
Note: a empty string ``` ""``` is falsy but the expression does not evaluate to a boolean. This can possible lead to a component rendering oddly. To deal with this we can convert to a boolean by doing !! before the string like ```!!sold```
Ternary conditions takes advantage of ``` ? : ``` and follows the logic of if then. 
Example:  
```
function Card({ title, subtitle }) {
  return (
    <div style={styles.card}>
      <h1 style={styles.title}>{title}</h1>
      {subtitle ? (
        <h2 style={styles.subtitle}>{subtitle}</h2>
      ) : (
        <h3 style={styles.empty}>No subtitle</h3>
      )}
    </div>
  )
}
```
In this example if subtitle is not null then a H2 with given subtitle appears else it appears with No subtitle. ? follows the truth and : follows the negation or else.
We can also use if/else within React elements for further complexity. 
Example:
```
function Card({ loading, error, title, subtitle }) {
  let content

  if (error) {
    content = 'Error'
  } else if (loading) {
    content = <h3 style={styles.empty}>Loading...</h3>
  } else {
    content = (
      <div>
        <h1 style={styles.title}>{title}</h1>
        {subtitle ? (
          <h2 style={styles.subtitle}>{subtitle}</h2>
        ) : (
          <h3 style={styles.empty}>No subtitle</h3>
        )}
      </div>
    )
  }
  ```
In this example there is an if else conditional where the else option is the ternary example from above.
### Lists and Keys
Every react element can be passed the prop key. React uses key to determine the rendered elements identity. This helps us manage DOM more efficiently for example if we want to remove the first out of 15 posts on a website. 
Internally React assigns an unique id to each element in order to match its order for rendering. The id of element is the id of its parent concatenated with the index of the element within its parent.
Example 
```
<div>  # 0
  <button/> #0.0  
  <button/> #0.1
</div>
<button/> # 1
```
However we can also customarily set the key value for example ```<div key="title"></div>``` has a identity #title

Rendering Components through mapping an array of data
``` const data {
  { name: "John", age: 20},
  { name: "Doe", age: 24},
}
export default () => {
  <div>
    {data.map(item => {
      <div>{item.name}</div>
    })}
  </div>
}
```
This would return as two divs each containing the names "John" and "Doe"
If our data had a unique identifier it would be the best to use something like that for example:  
``` const data {
  { name: "John", age: 20, id: 0},
  { name: "Doe", age: 24, id: 1},
}
export default () => {
  <div>
    {data.map(item => {
      <div key={item.id}>{item.name}</div>
    })}
  </div>
}
```
If no identifier is given it will use map index as a key. This can be bad when new data is added to the mapping. If possible assign a key. Note that we want this to be a string.
Example:  
```
<div>
  {data.map((item, index) => (
    <div key={index.toString()}>{item.name}</div>
  ))}
</div>
```
### Hooks
Hooks are specially implemented functions that led us add functionality to React components beyond just creating React elements

Hooks are different then regular functions and must be written in a specific way. For more information check [Here](https://reactjs.org/docs/hooks-rules.html)

### UseState
useState lets us "remember" a value within a component function. A component function may called many times thus var or let may get reset. React can remember state variables with UseState.

The useState hook takes a single argument our initial state and returns an array containing two elements: state: the current state, setState a function to update our state. UseState hook can store any type of value, number, string, array, object
Example:
``` const [dogAge setdogAge] = useState(2)```
<br/>
Array Example:
``` 
const [dogs setDogs] = useState(["Cody", "Harley"]) 
// Interacting with SetDogs
setDogs([...dogs, "Timmy"])
```
Further Example:

```
import React, { useState } from 'react'
import { render } from 'react-dom'

const randomDiceRoll = () => {
  return Math.floor(Math.random() * 6) + 1
}

export default function App() {
  const [diceRolls, setDiceRolls] = useState([1, 2, 3])

  return (
    <div>
      <button
        onClick={() => {
          setDiceRolls([...diceRolls, randomDiceRoll()])
        }}
      >
        Roll dice
      </button>
      <ul>
        {diceRolls.map((diceRoll, index) => (
          <li key={index}>{diceRoll}</li>
        ))}
      </ul>
    </div>
  )
}

render(<App />, document.querySelector('#app'))
```
Note: In the last two examples concerning array we are not pushing an element to the array diceRools but return a new array of the two. We do this to make sure we are detect changes to the data as not doing this we might not realize there have been changes to an array.
### UseReducer
Similar to useState but gives a more structured approach for updating complex values. It is most commonly used when our state has multiple sub-values like an objecting containing keys we want to update independently.  
useReduced takes 2 arguments with an optional 3rd, reducer: a pure function that takes a state and an action and returns a new state value based on action, and intialState value, and initializer (optional), it returns the current state as well a dispatch function to update the state.
Dispatch function takes an action calls the reducer to update the state
Example:
```
import React, { useReducer } from 'react'
import { render } from 'react-dom'

const types = {
  PET: 'PET',
  COLOR: 'COLOR',
}

const reducer = (state, action) => {
  switch (action.type) {
    case types.PET:
      return { ...state, pet: action.value }
    case types.COLOR:
      return { ...state, color: action.value }
  }
}

const initialState = {
  color: 'black',
  pet: 'cat',
}

export default function App() {
  const [state, dispatch] = useReducer(reducer, initialState)

  return (
    <div>
      <label>Choose a color and a pet: </label>
      <br />
      <select
        value={state.color}
        onChange={event => {
          dispatch({ type: types.COLOR, value: event.target.value })
        }}
      >
        <option value="black">Black</option>
        <option value="pink">Pink</option>
        <option value="blue">Blue</option>
      </select>
      <select
        value={state.pet}
        onChange={event => {
          dispatch({ type: types.PET, value: event.target.value })
        }}
      >
        <option value="cat">Cat</option>
        <option value="dog">Dog</option>
        <option value="mouse">Mouse</option>
      </select>
      <br />
      <br />
      You chose a {state.color} {state.pet}
    </div>
  )
}

render(<App />, document.querySelector('#app'))
```
Note:
use ```useState``` for simple state like js types  
use ```useReducer``` when there are subvalue that depend on each other

### useEffect
we use the useEffect hook for calling functions with side effects within our components
UseEffect has 2 arguments: callback a function with side effects, and dependencies an optional array containing dependency values

```
import React, { useState, useEffect } from 'react'

export default function App() {
  const [count, setCount] = useState(0)
  const color = count % 5 === 0 ? 'red' : 'blue'

  useEffect(() => {
    document.body.style.backgroundColor = color
  }, [color])

  return (
    <button
      onClick={() => {
        setCount(count + 1)
      }}
    >
      Click HERE to increment: {count}
    </button>
  )
}
```
In this example useEffect is called every time the color changes. This in effect happens every time we iterate and click the button calling setCount. If we do not have a dependency array our callback will run every time the component function runs. Rather if our dependency is empty ```[]``` it will only run once.
Example:  
```
import React, { useState, useEffect } from 'react'
import { render } from 'react-dom'

function randomColor() {
  return `#${Math.random()
    .toString(16)
    .substr(-6)}`
}

function App() {
  const [count, setCount] = useState(0)

  useEffect(() => {
    document.body.style.backgroundColor = randomColor()
  }, [])

  return (
    <button
      onClick={() => {
        setCount(count + 1)
      }}
    >
      Click HERE to increment: {count}
    </button>
  )
}

render(<App />, document.querySelector('#app'))
```
### UseMemo && useCallback
useMemo hook lets use memoize values and useCallback lets us memoize functions. The return values will be the same function. This could allow us to use a function as a dependency for another hook. 
### useRef
useRef hooks allows us to create a mutable value that exists for the lifetime of the component.  We begin by wrapping a value like ``` const myRef = useRef(42)``` we can then use ```myref.current``` to access or update the value.
All react components can be passed a ref prop in which case React will automatically assign the instance of the component to myRef.current. 
Example:
```
import React, { useState, useRef, useEffect } from 'react'
import { render } from 'react-dom'

function App() {
  const intervalRef = useRef()
  const [count, setCount] = useState(0)

  useEffect(() => {
    intervalRef.current = setInterval(() => setCount(count => count + 1), 1000)

    return () => {
      clearInterval(intervalRef.current)
    }
  }, [])

  return (
    <>
      <div style={{ fontSize: 120 }}>{count}</div>
      <button
        onClick={() => {
          clearInterval(intervalRef.current)
        }}
      >
        Stop
      </button>
    </>
  )
}

render(<App />, document.querySelector('#app'))
```
### useContext
allows us to pass values to deeply nested components

Still not too sure on this one.
Example from the website:
```
import React, { useContext, createContext } from 'react'

const ThemeContext = React.createContext()

function Title() {
  const theme = useContext(ThemeContext)

  const style = {
    background: theme.primary,
    color: theme.text,
  }

  return <h1 style={style}>Title</h1>
}

function Nested() {
  return <Title />
}

function NestedTwice() {
  return <Nested />
}

export default function App() {
  const theme = {
    primary: 'dodgerblue',
    text: 'white',
  }

  return (
    <ThemeContext.Provider value={theme}>
      <NestedTwice />
    </ThemeContext.Provider>
  )
}
```