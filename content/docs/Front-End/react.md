---
title: React
weight: 2
bookToc: true
---

# React
---

## Notes

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
This is nice as it allows for the full power of CSS and is straightforward, however it is hard with large codebases, the compoents are not self-contained in a single js file and it works for DOM renderer only (No Native).

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
<code>
<input
    onChange = { e => {
        console.log(e)
    }}>
</input>
</code>