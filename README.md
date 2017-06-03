# network
A react component to visualise a graph of nodes and edges for the given data. It is based on vis.js library. 


## Installation

To install this Component, run `yarn add network` or `npm install network`., Don't forget to install vis.js by running `yarn add vis`.


## Usage

To use the component, In your react Application just do

```javascript
import React from 'react';
import Network from 'network';

const MyComponent = (props) => {

    return (
        <Network
            outgoing='true'
            root='MainNode'
            subNodes=['Awesome', 'Graph', visualizations']
        />
    );

}

export default MyComponent;

```
