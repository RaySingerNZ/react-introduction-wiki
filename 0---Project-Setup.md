```
git checkout step-0
```

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

This will launch your browser and you can see the static version of the site. This is a simple master-detail
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

## The Root Component

In the application there is a file `src/index.js` where our application is bootstrapped. Although (as explained later) React does not use HTML templates we do need to tell React where in our `index.html` file we would like to render our app.

This is done in using the `ReactDOM` library which is allows React components to use the DOM as a render target. If you look in index.js you will see the following:

``` javascript
import React from 'react'
import ReactDOM from 'react-dom'

ReactDOM.render(
  <div className="App">
    Hello World!
  </div>,
  document.getElementById('root')
)
```

First we have imported both React (this must be in scope if using and JSX) and ReactDOM. Then we have called the [`ReactDOM.render()`](https://facebook.github.io/react/blog/2015/10/01/react-render-and-top-level-api.html) method. This method takes as a first argument a single component or HTML node and as a second argument the HTML DOM element that the app is to be rendered in. 

In this case we are telling it to render a div with "Hello World!" inside it into the element that has an `id` of `root`.  In `index.html` we have this element:

``` html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>React App</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/0.97.7/css/materialize.min.css">
  </head>
  <body>
    <div id="root"></div>
  </body>
</html>
```

If you run `npm start` from your command line then you will see this render as a blank page with the "Hello World!" Message at the top left, just like a normal HTML page.

This should reload when you make changes or switch branches but sometimes the `create-react-app` build configuration doesn't work and you need to restart it. There are better build systems (or custom ones) but I've used this to keep the noise to a minimum and just focus on React and React Router.