## Composition vs Inheritance
### https://reactjs.org/docs/composition-vs-inheritance.html
- composition instead of inheritance to reuse code between components
  - components can pass arbitrary children to others by nesting the JSX
  - components defined as classes


## useReducer
### https://reactjs.org/docs/hooks-reference.html#usereducer
- alternatve to useState
  - good to use when new state depends on previous
``const [state, dispatch] = useReducer(reducer, initialArg, init);``
- set initial state in second argument:
```
const [state, dispatch] = useReducer(
    reducer,
    {count: initialCount}
  );
  ```
 - useDebugValue can be used to display a label for custom hooks in React DevTools
  - most valuable for custom Hooks that are part of shared libraries
  
## Redux 3 Principles
### https://redux.js.org/understanding/thinking-in-redux/three-principles
1. One Source of Truth:
  - global state of your application is stored in an object tree within a single store
  - makes it easy to create universal apps, as the state from your server can be serialized and hydrated into the client with no extra coding effort
  - easier to debug
  - can persist app state (undo/redo)
2. State is Read Only:
- only way to change state is to emit action
- all changes happen one at a time and in order
3. Changes Made with Pure Functions:
  - Reducers are just pure functions that take the previous state and an action, and return the next state
  
## Redux Core Concepts
### https://redux.js.org/introduction/core-concepts
- state is like an object (no setters)
  - so that different parts of the code can’t change the state arbitrarily, causing hard-to-reproduce bugs
  - to change, emit an action = plain JS object
    - Enforcing that every change is described as an action lets us have a clear understanding of what’s going on in the app
  - reducer functions = a function that takes state and action as arguments, and returns the next state of the app
    - small functions for parts of state
