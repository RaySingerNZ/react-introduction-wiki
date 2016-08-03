# Detail View

Now we will tie up the whole thing by make this single view and the link to it work. Before
we look at the single view notice how the LocationCard component has been updated build up the
link path dynamically using the locations id:

``` javascript

<Link className="btn" to={"locations/" + location.id}>Read more</Link>

```

We also have created a LocationDetail component which is a simple function that takes location as props
and displays the single page:

```

import React, { PropTypes } from 'react'
import { Link } from 'react-router'

const LocationCard = ({location}) => (
    <div className="col s12 m6">
        <div className="card">
            <div className="card-image">
                <img src={location.images.rectangle} alt={location.name}/>
                <span className="card-title">{location.name}</span>
            </div>
            <div className="card-content">
                <p>{location.shortDescription}</p>
            </div>
            <div className="card-action">
                <Link className="btn" to={"locations/" + location.id}>Read more</Link>
            </div>
        </div>
    </div>
)

LocationCard.propTypes = { 
    location: PropTypes.object.isRequired
}

export default LocationCard


```

Now we have a basic master/detail New Zealand scenic locations app!