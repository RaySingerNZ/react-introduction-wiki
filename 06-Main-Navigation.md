```
git checkout step-4
```

So far the main navigation has been hard coded into our App component. Lets move this into its own component as well

``` javascript

//MainNavigation.js
import React from 'react'

const MainNavigation = ({location}) => (
    <nav>
        <div className="nav-wrapper teal ">
            <div className="container">
            <a href="#" className="brand-logo">New Zealand Scenic Locations</a>
            <ul id="nav-mobile" className="right hide-on-med-and-down">
                <li><a href="/">Home</a></li>
            </ul>
            </div>
        </div>
    </nav>
)

export default MainNavigation

```

We haven't really done much except move the markup out. But now in App.js its looking more tidy:

``` javascript

import React, { Component } from 'react'
import './App.css'
import locations from './api/locations'

// Components
import LocationCard from './components/LocationCard'
import MainNavigation from './components/MainNavigation'

class App extends Component {
  render() {
    return (
      <div className="App">
            <MainNavigation/>
            <div className="container main-content">      
              <div className="row">
                  {locations.map((location) => {
                    return <LocationCard key={location.id} location={location} />
                  })}
              </div>
            </div>
      </div>
    )
  }
}

export default App

```
