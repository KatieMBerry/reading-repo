## setState 
### https://css-tricks.com/understanding-react-setstate/
- pass an object to setState() => the object contains the part of the state we want to update 
- reconciliation process is the way React updates the DOM, by making changes to the component based on the change in state
  - updated copy tree is created and elements are compared to original to see what parts of UI need rerendering
    - this is what makes react fast
- can pass functions or objects to setState()
  - pass a function when you can to update state multiple times
- updater allows you access the current state and put it to use immediately to update other items
  - don't depend on this.state immediately after calling setState() and make use of the updater function instead

## Lists & Keys 
### https://reactjs.org/docs/lists-and-keys.html
- can build collections of elements and include them in JSX using curly braces
- components can accept an array of numbers and output a list of elements
- "key” is a unique string attribute to include when creating lists of elements (uniqueness among siblings, not globally)
  - keys help React identify which items have changed, are added, or are removed
  - when no stable IDs for rendered items, can use the item index as a key as a last resort(but not good practice)
  - only make sense in the context of the surrounding array
    - good rule of thumb is that elements inside the map() call need keys
    
## Typechecking 
### https://reactjs.org/docs/typechecking-with-proptypes.html
- React has some built-in typechecking abilities
  - to run typechecking on the props for a component, you can assign the special propTypes property
    - PropTypes exports a range of validators that can be used to make sure the data you receive is valid
    - For performance reasons, propTypes is only checked in development mode
```import PropTypes from 'prop-types';

class Greeting extends React.Component {
  render() {
    return (
      <h1>Hello, {this.props.name}</h1>
    );
  }
}

Greeting.propTypes = {
  name: PropTypes.string
};

// Specifies the default values for props:
Greeting.defaultProps = {
  name: 'Stranger'
};
```
## Components & Props
### https://reactjs.org/docs/components-and-props.html
- components are like JavaScript functions b/c they accept arbitrary inputs (called “props”) and return React elements describing what should appear on the screen
- can write as function or class component syntax
- When React sees an element representing a user-defined component, it passes JSX attributes and children to this component as a single object
  - this object = “props”
  - name props from the component’s own point of view rather than the context in which it is being used
  - all React components must act like pure functions with respect to their props
    - State allows React components to change their output over time in response to user actions, network responses, and anything else, without violating this rule

## Handling Events 
### https://reactjs.org/docs/handling-events.html
- with JSX you pass a function as the event handler, rather than a string
- binding is necessary to make `this` work in the callback
``this.handleClick = this.handleClick.bind(this);``

## Snapshot Testing
### https://jestjs.io/docs/en/snapshot-testing
- to ensure UI doesnt change unexpectedly
- a typical snapshot test case renders a UI component, takes a snapshot, then compares it to a reference snapshot file stored alongside the test
  - you can use a test renderer to quickly generate a serializable value for your React tree
- for intentional implementation changes, need to update our snapshot artifacts
  - can run Jest with a flag that will tell it to re-generate snapshots ``jest --updateSnapshot``
  
