## Model–view–controller
### https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller
- object-oriented design pattern for developing UI that breaks down logic into 3 elements:
  1. Controller- used by user
    - Accepts input and converts it to commands for the model or view 
    - responds to the user input and performs interactions on the data model objects
  2. Model - manipulated by controller; receives user input via controller
    - central componenet
    - manages the data, logic and rules 
  3. View - updated by model and displayed back to user
    - any visual representation of information
    
 ## 4 Layers of Single Page Applications
 ### https://hackernoon.com/architecting-single-page-applications-b842ea633c2e
 - Architecture of React App:
  Domain > Store > Application > View
  
  - View: presentational & container components
  - Application Services: interpret state & orchestrates operations
  - Store: holds state as immutable, publishes and notifies about state changes
  - Domain: represents state & encapsulates logic
 - "Immutability makes tracking changes cheap. A change will always result in a new object so we only need to check if the reference to the object has changed"
 - Object.freeze() method prevents new properties from being added to an object
 
 ## MVP Pattern for React
 ### https://blog.testdouble.com/posts/2019-11-04-react-mvc/
 - Hooks: helps pull behavior into common locations, re-use that behavior across other components, and catch prop-state syncing bugs 
 - The MVC pattern in React breaks down into the following two pillars:
    1. Presentation Layer of Controller and View React Components
    2. A UI-Agnostic Data Model

## Reconciliation
### https://reactjs.org/docs/reconciliation.html
- React provides a declarative API so that you don’t have to worry about exactly what changes on every update
- Whenever the root elements have different types, React will tear down the old tree and build the new tree from scratch
- When comparing two React DOM elements of the same type, React looks at the attributes of both, keeps the same underlying DOM node, and only updates the changed attributes.
- React updates the props of the underlying component instance to match the new element, and calls UNSAFE_componentWillReceiveProps()
- React supports a key attribute. When children have keys, React uses the key to match children in the original tree with children in the subsequent tree
