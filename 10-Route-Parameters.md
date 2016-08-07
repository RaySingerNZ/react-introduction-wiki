```
git checkouts step-10
```

First things first I need to create the container component for my employee profile page. I have created
the file `src/containers/EmployeeProfile`. I am going to take a different approach and slowly take out the html
as I break it down into its compnents. My bare bones `EmployeeProfile` looks like this:

``` javascript
import React, { Component } from 'react'

class EmployeeProfile extends Component {
    render(){
        return (
            <div>
            </div>
        )
    }
}

export default EmployeeProfile
```