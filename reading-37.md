## Redux Middleware
### https://redux.js.org/tutorials/fundamentals/part-4-store#middleware
- lets us customize the dispatch function
- Redux middleware provides a third-party extension point between dispatching an action, and the moment it reaches the reducer
  - for logging, crash reporting, talking to an asynchronous API, routing, etc
  - written as a series of three nested functions
      - exampleMiddleware: The outer function is actually the "middleware" itself. It will be called by applyMiddleware, and receives a storeAPI object containing the store's {dispatch, getState} functions. These are the same dispatch and getState functions that are actually part of the store. If you call this dispatch function, it will send the action to the start of the middleware pipeline. This is only called once.
      - wrapDispatch: The middle function receives a function called next as its argument. This function is actually the next middleware in the pipeline. If this middleware is the last one in the sequence, then next is actually the original store.dispatch function instead. Calling next(action) passes the middleware to the next middleware in the pipeline. This is also only called once
      - handleAction: Finally, the inner function receives the current action as its argument, and will be called every time an action is dispatched
      
  - Outer: someCustomMiddleware (or whatever your middleware is called)
    Middle: wrapDispatch
    Inner: handleAction
 - can be written as arrow functions
 - Any middleware can return any value, and the return value from the first middleware in the pipeline is actually returned when you call store.dispatch()
 - use cases: A middleware can do anything it wants when it sees a dispatched action:

      - Log something to the console
      - Set timeouts
      - Make asynchronous API calls
      - Modify the action
      - Pause the action or even stop it entirely
 - DevTools - an addon that shows you a history of what actions were dispatched, what those actions contained, and how the state changed after each dispatched action
 ``redux-devtools-extension``
