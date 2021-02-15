## Redux Motivation
### https://redux.js.org/understanding/thinking-in-redux/motivation
- when mutations and asynchronous combine, it creates a mess
  - Libraries like React attempt to solve this problem in the view layer by removing both asynchrony and direct DOM manipulation. However, managing the state of your data is left up to you. This is where Redux enters.
  - Redux attempts to make state mutations predictable by imposing certain restrictions on how and when updates can happen
  
  
## Redux Concepts and Data Flow
### https://redux.js.org/tutorials/fundamentals/part-2-concepts-data-flow
- "one-way data flow":
  - State describes the condition of the app at a specific point in time
  - The UI is rendered based on that state
  - When something happens (such as a user clicking a button), the state is updated based on what occurred
  - The UI re-renders based on the new state
      - when multiple components that need to share and use the same state, this can break down
        - One way to solve this is to extract the shared state from the components, and put it into a centralized location outside the component tree
        - By defining and separating the concepts involved in state management and enforcing rules that maintain independence between views and states, we give our code more structure and maintainability
        - Redux: a single centralized place to contain the global state in your application, and specific patterns to follow when updating that state to make the code predictable
- Redux expects that all state updates are done immutably
 - to update values immutably, your code must make copies of existing objects/arrays, and then modify the copies (like spreading, etc)
- action = plain JavaScript object that has a type field that gives descriptive name "feature/action"
  - an event that describes something that happened in the application
  - payload = action object can have other fields with additional information about what happened
- reducer = a function that receives the current state and an action object, decides how to update the state if necessary, and returns the new state: (state, action) => newState
  - reducer rules:
    - should only calculate the new state value based on the state and action arguments
    - not allowed to modify the existing state. Instead, they must make immutable updates, by copying the existing state and making changes to the copied values.
    - must not do any asynchronous logic, calculate random values, or cause other "side effects"
  - reducer logic:
    1. Check to see if the reducer cares about this action
    2. If so, make a copy of the state, update the copy with new values, and return it
    3. Otherwise, return the existing state unchanged
- store = object where current Redux application state lives
  - created by passing in a reducer, and has a method called getState that returns the current state value
  - dispatch = only way to update the state is to call store.dispatch() and pass in an action object (triggers event)
- Selectors = functions that know how to extract specific pieces of information from a store state value
  - can help avoid repeating logic
  
## Redux State, Actions, and Reducers
### https://redux.js.org/tutorials/fundamentals/part-3-state-actions-reducers
- example todo app
      
