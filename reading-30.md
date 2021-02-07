## Hooks API
### https://reactjs.org/docs/hooks-reference.html
- React Hooks = let you use state and other React features without writing a class
- useState: ``const [state, setState] = useState(initialState);``
- setState: ``setState(newState);``
  -the first value returned by useState will always be the most recent state after applying updates
- initialState argument is the state used during the initial render
- useEffect: function passed to useEffect will run after the render is committed to the screen ``useEffect(didUpdate);``
  - the function passed to useEffect fires after layout and paint, during a deferred event. This makes it suitable for the many common side effects, like setting up subscriptions and event handlers, because most types of work shouldn’t block the browser from updating the screen


## State Hooks
### https://reactjs.org/docs/hooks-effect.html
- hooks: They let you use state and other React features without writing a class
- effect hook: lets you perform side effects in function components
  - you tell React that your component needs to do something after render
side effects = Data fetching, setting up a subscription, and manually changing the DOM in React components
  - you can think of useEffect Hook as componentDidMount, componentDidUpdate, and componentWillUnmount combined
  - some require cleanup while others dont
    - dont require running additional code: Network requests, manual DOM mutations, and logging are common examples
 - React performs the cleanup when the component unmounts
 
 ## State Hook
 ### https://reactjs.org/docs/hooks-state.html
 - Hooks don’t work inside classes. But you can use them instead of writing classes
 - A Hook is a special function that lets you “hook into” React features
 - The only argument to the useState() Hook is the initial state
  - ex: useState is a Hook that lets you add React state to function components (which are usually stateless)
    - ``import React, { useState } from 'react';//declares a state variable
    function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);``
  - returns a pair of values: the current state and a function that updates it
  
## Hooks...
### https://reactjs.org/docs/hooks-overview.html
-  array destructuring syntax lets us give different names to the state variables we declared by calling useState
- Effects may also optionally specify how to “clean up” after them by returning a function
- Hooks are JavaScript functions, but they impose two additional rules:

    - Only call Hooks at the top level. Don’t call Hooks inside loops, conditions, or nested functions
    - Only call Hooks from React function components. Don’t call Hooks from regular JavaScript functions
    
- state of each component is completely independent. Hooks are a way to reuse stateful logic, not state itself
  
