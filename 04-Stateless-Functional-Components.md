```
git checkout step-2
```

A well established pattern in developing scalable React apps is creating a separation between presentational components and container components. This can be 
thought of also as 'dumb' and 'smart' components.

**Container** components are responsible for things like orchestrating user interaction, initiating and retrieving the data among other view logic related things. 
While **presentation** components are simple pure functions that take the current state and create a rendered representation of it.

If you open up `/src/components/EmployeeListItem.js` you will see the following:

``` javascript
import React from 'react'

const EmployeeListItem = () => (
    <li class="collection-item avatar">
        <img src="../src/images/gabriella-boone.png" alt="" class="circle" />
        <span class="title">Gabriella Boone</span>
        <p>.NET developer <br/>
        Modern Apps
        </p>
        <a href="gabriella-boon.html" class="secondary-content btn black">
            <i class="material-icons left">description</i>
            View C.V.
        </a>
    </li>
)

export default EmployeeListItem
```

This is a `stateless functional component` which means it is just a function that returns a component heirarchy to render.
These types of components are pure functions of the current state. In the above example we are just returning some static
markup but using what React calls `props` and you can see more about these in the [next step]()