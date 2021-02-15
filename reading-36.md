## Redux Guide
### https://www.freecodecamp.org/news/understanding-redux-the-worlds-easiest-guide-to-beginning-redux-c695f45546f6/
- Redux is a predictable state container for JavaScript apps
- Redux store will be responsible for managing the App’s state
```
import { createStore } from "redux"; //an import from the redux library
const store = createStore();
```
  - takes in a reducer/reducing function (only mandatory argument)
    - can also take in initialState
  - takes in state and action
    - REDUCER always “talks” to the STORE
    - reducer function will be in the path src/reducers/index.js 
    - always returns the new state 
    - do not mutate the state received in your Reducer; always return a new copy of the state
 - 3 methods for createStore
  - getState - returns current state
    - Where Store is a valid Redux STORE
 - common to create three different folders within your app directory, and name each after these actors: store, action, reducers
  - each of the folders, create an index.js file. This will be the entry point for each of the Redux actors
 - dispatchBtnAction = dispatch an action when a click has happened
- whatever store you create has a subscribe method called like this: store.subscribe()
  - subscribes to updates
  - argument passed into store.subscribe() is a function, and it will be invoked whenever there’s a state update
  ```
  const render = function() {
  ReactDOM.render(<App />, document.getElementById("root")
}
```
