```
git checkout step-2
```

In React there is a general concept of having 'dumb' and 'smart' compeonents. Or 'container' and 'presentational'
components. The distinction is in their relationship with the state of the applicaiton.

**Container** components are responsible for orchstrating and retrieving the data. While **presentational**
components are simple pure functions that render UI elements using properties passed down to them through
what are called `props`.

If you open up `/src/components/LocationCard.js` you will see the following:

```
import React from 'react'

const LocationCard = () => (
    <div className="col s12 m6">
        <div className="card">
            <div className="card-image">
                <img src="/src/images/huka-falls-rect.jpg" alt="Huka Falls"/>
                <span className="card-title">Huka Falls</span>
            </div>
            <div className="card-content">
                <p>The Waikato River, New Zealand's longest river, moves gracefully north from Lake Taupo between banks 100 metres apart.</p>
            </div>
            <div className="card-action">
                <a className="btn" href="single-huka-falls.html">Read more</a>
            </div>
        </div>
    </div>
)

export default LocationCard
```

At the moment we have just moved the HTML into this component and replace all the HTML in `App.js` with one instance
of the LocationCard component.