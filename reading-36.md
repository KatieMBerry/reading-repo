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
- Lodash = library for iterating over objects
- file structure:
  1. Create two folders: containers and components.
  2. App.js attempts to retrieve contacts from the store. So, move App.jsand App.css to the containers folder.
  3. Move Sidebar.js, Sidebar.css , Main.js and Main.css to the components folder. They do not talk to Redux directly for anything.
  4. Please do not move Index.js and Index.css. Those are the entry point of the App. Just leave those at the root of the project directory.
  5. Please move User.js and User.css to the containers directory. The User component does NOT talk to Redux yet but it will. Remember that when the App is completed, upon clicking a user from the sidebar, their messages will be shown. By implication, an action will be dispatched
  
## Hooks in React Redux
### https://react-redux.js.org/next/api/hooks
- wrap your entire application in a <Provider> component to make the store available throughout the component tree
- useSelector() will subscribe to the Redux store, and run selector whenever an action is dispatched
- With hooks, there is no way to render a context provider, which means there's also no nested hierarchy of subscriptions. Because of this, the "stale props" and "zombie child" issues may potentially re-occur in an app that relies on using hooks instead of connect()
  - useSelector() tries to deal with this by catching all errors that are thrown when the selector is executed due to a store update (but not when it is executed during rendering)
 
