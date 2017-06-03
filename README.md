# network-vis
A react component to visualise a graph of nodes and edges for the given data. It is based on vis.js library. Currently, only string nodes are supported.  


## Installation

To install this Component, run `yarn add network_vis` or `npm install network_vis`., Don't forget to install vis.js by running `yarn add vis`.


## Usage

To use the component, In your react Application just do

```javascript
import React, { Component } from 'react';
import Network from 'network-vis';

const containerStyle = {
  width: '100vh',
  height: '100vh',
}

class MyComponent extends Component {

    constructor(props) {
      super(props);
      this.state = {
        listOfNodes: [],
      }
    }

    async handleNodeClick(node) {
      try {
        const jsonPromise = await fetch('url for fetching array of strings for each clicked node');
        this.setState({
            listOfNodes: await jsonPromise.json(),
        });
      } catch (err) {
          console.log('failed');
      }
    }

    return (
      <div style={containerStyle}>
        <Network
            outgoing='true'
            root='MainNode'
            subNodes={this.state.listOfNodes}
            onNodeClick={this.handleNodeClick}
        />
      </div>
    );

}

export default MyComponent;

```
