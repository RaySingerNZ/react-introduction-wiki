# Component Props

Components have what are called `props` which look a lot like HTML attributes except are camel case
instead of snake case. For example

``` javascript

<MyComponent myProp="hello!"></MyComponent>

```

The component would recieve these props like this:

``` javascript

// Using a class based component
class MyComponent extends Component {
    constructor(props){

    }
    render(){
        <div>
            {props.myProp}
        </div>
    }
}

//Using a pure function and parameter deconsstruction
const LocationCard = ({myProp}) => (
    render(){
        <div>
            {myProp}
        </div>
    }
)
```

As you can see you can render values from variables by putting them insdie paretheses `{}`. This can be seen in our app
in the `LocationCard` component:

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

You can also see above the use of `PropTypes` which is part of the core React library and allows you 
to define what primative types or define shapes of the props being passed into your component.

In this example I have sat that there will be an `object` and i have also defined that is required. If the 
component doesn't recieve the prop or its the wrong type/shape then an error will show in the console.

## Multiple Locations

Also now in `src/App.js` imported a simple mock API from `src/location` which means I have an array of 
locations available in my `container` component `App`.

Since React is just JavaScript we can use plain old vanila JavaScript to do things like loop through our array. For example
to show a LocationCard for each item in the location array I can do this:

```
<div className="container main-content">      
    <div className="row">
        {locations.map((location) => {
        return <LocationCard key={location.id} location={location} />
        })}
    </div>
</div>
```

Notice how I have added a `key` prop to my LocationCard component. This is an internal React thing that allows it to
more efficiently track changes in the state of your application. It just needs to be a unique identifier for each
item in the collection.