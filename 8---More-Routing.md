```
git checkout step-6
```

Since a lot of our apps are going to have something like a navigation or some sort of shared
UI components it quite useful to have a root component that acts as an outlet for showing 
different routes.

We've done this in this step by creating a new folder `src/containers` where we put our new `LocationList`
component which is basically the location list part of our `App` component:

``` javascript

import React, { PropTypes } from 'react'

const LocationCard = ({location}) => (
    <div className="col s12 m6">
        <div className="card">
            <div className="card-image">
                <img src={location.images.square} alt={location.name}/>
                <span className="card-title">{location.name}</span>
            </div>
            <div className="card-content">
                <p>{location.shortDescription}</p>
            </div>
            <div className="card-action">
                <a className="btn" href="#">Read more</a>
            </div>
        </div>
    </div>
)

LocationCard.propTypes = { 
    location: PropTypes.object.isRequired
}

export default LocationCard

```

Then in our index.js where we define our routes we have this:

``` javascript

import React from 'react'
import ReactDOM from 'react-dom'
import { Router, Route, IndexRoute, browserHistory  } from 'react-router'

// Main app wrapper component
import App from './App'

// Container Views
import LocationList from './containers/LocationList'

ReactDOM.render(
  <Router history={browserHistory}>
    <Route path="/" component={App}>
      <IndexRoute component={LocationList} />
    </Route>
  </Router>,
  document.getElementById('root')
)


```

Here we use the nesting of the Route components to describe the heirarchy of our routes. In this case we have main router
that will render our root `App` component. Then as a child Route of this we have a new component `IndexRoute` to 
define our location list route. This IndexRoute component just defines the default route if there are no other matches.

When you nest them like this the `LocationList` component (the child route) gets passed to the `App` component (the base route)
as children. So you can then access it like this in `src/App.js`:


``` javascript
import React, { Component } from 'react'
import './App.css'

// Components
import MainNavigation from './components/MainNavigation'

class App extends Component {
  render() {
    return (
      <div className="App">     
          <MainNavigation/>
          <div className="container main-content">      
              {this.props.children}
          </div>
      </div>
    )
  }
}

export default App

```
This way the App component acts as an outlet for the child routes within it.
