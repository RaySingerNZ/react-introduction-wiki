# Project Setup

This project has been setup using the [Create React App](https://github.com/facebookincubator/create-react-app)
to keep it very simple and shows off the basic features of [React](https://facebook.github.io/react/) 
and [React Router](https://github.com/reactjs/react-router).

Make sure you have followed the instructions about [getting started in the readme here](https://github.com/justsayno/react-introduction)

## Introduction

We are going to start with an html verion of the final simple showcase of 
scenic New Zealand locations displayed using [MaterializeCss](http://materializecss.com/).

To have a look at this run the command

```
npm run static
```

This will launch your browser and you can see the static version of hte site. This is a simple master-detail
design where you can click through to see more information about the locations.

## Coding along

This project is setup so that you can use the branches to code along with each step. To go to the start run the following:

```
git checkout step-0
```

This will leave you with a bare bones version of the project.

### Project Structrure

``` 
React-Introduction/
 ├──src/                * Where all the app development files are
 |   ├──api/            * Simple mock api for location data
 │   │
 |   ├──images/         * The images for the site
 │   │ 
 |   ├──App.css/        * The main stylesheet for the app
 │   │  
 |   ├──App.js/         * The root app component
 │   │  
 |   └──index.js/       * The entry point to our application where we bootstrap
 |
 ├──Static/             * The static HTML that we start with
 │   │ 
 |   └──...             * The root entry file for the application
 |
 └──....                * Tests for the application
```

## Our first component

Our root basic component looks like this:

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

