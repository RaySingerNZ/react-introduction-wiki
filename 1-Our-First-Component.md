Following on from our last step we have now introduced our first React Component. Our root basic component looks like this:

``` jsx

import React, { Component } from 'react'
import './App.css'

class App extends Component {
  render() {
    return (
      <div className="App">
         
      </div>
    )
  }
}

```

This is simply a class that extends the React class [Component](https://facebook.github.io/react/docs/component-api.html).
At the top we are importing the React library as well as using es2015's new [destructuring](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)
to get a reference the Component class at the same time.

Components are simple classes that have various life cycle events in the process that React
goes through when state changes and html is rendered. The also have a `render()` function
which is where you put your JSX that represents the HTML and components that make up your 
app.

### Wiring up our app

Building React apps is a process of making components and nesting them within one another to create
a full application. But at the top level you need to do some plubming to att

In our `index.js` file we import the core React library, the ReactDom library and the root `App`
component from our file `App.js`. We then use the function `ReactDom.render()` which takes a 
single React component and 

``` jsx

import React from 'react'
import ReactDOM from 'react-dom'
import App from './App'

ReactDOM.render(
  <App />,
  document.getElementById('root')
)

```

When your app if bundled up using the `npm start` command the entry point is this file which mounts your
root component (in this call `<App />`) into the select DOM node on the page.

