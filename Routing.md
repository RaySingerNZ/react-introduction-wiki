# Routing

```
git checkout step-5
```

So far we have only had one page we need to be able to use the `Read More` buttons and go to the detail
of the location. To do this we need to introduce a routing solution. We could write our own, since React
is not a framework its a library. But there is alerady a great one called [React Router](https://github.com/reactjs/react-router)

Essentially the Router that you get in React Router is just a component itself. It can take props just like
any other component and it has special props relating to configuring your applications routing.

In this step there is a very basic example of routing with React Router in `src/index.js`:

``` javascript

import React from 'react'
import ReactDOM from 'react-dom'
import { Router, Route, browserHistory  } from 'react-router'
import App from './App'

ReactDOM.render(
  <Router history={browserHistory }>
    <Route path="/" component={App}/>
  </Router>,
  document.getElementById('root')
)


```

Here we have imported the `Router` component, the `Route` component and `browserHistory` from React Router.
The Router is the root component while the Route component is used to describe each of the routes in your app.
Here we have passed in browserHistory to the Router component which will mean we are using HTML5 history API
URLs. You can also use a hash based url system as well for legacy support.

## The Route component

The route component can take a path (the relative url) amd a component (the component to render when the rout is 
matched) as props.