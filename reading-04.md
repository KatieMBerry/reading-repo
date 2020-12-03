# What is the Event Loop?
- call stack = one thread(one task at a time) = where we are in the task list
- blocking == code that's slow that's on the call stack and keeps other things on the stack from running 
  - async callbacks = one solution
 - event loop = one task at a time but JS delegates so things can be done concurrently
    - ex: callback from webAPI => task queue => event loop => pushes cb back onto stack to finish running
      setTimeout(function cb() {
      console.log('there');
      }, 0); 
        - ====> the event loop will wait for the stack to clear before pushing the cb back onto the stack to run, even though the timeout is 0
        - therefore, the setTimeout is not a guaranteed amount of time, but a minimum amoutn of time
  - browser can't render until the stack is clear, so blocking with slow, synchronous code blocks the event loop and keeps UI from rendering fluidly
  - stack can flood easily (ex: scrolling events)
  
# Promise
- promise states:
  - pending: initial state, neither fulfilled nor rejected.
  - fulfilled: meaning that the operation was completed successfully.
  - rejected: meaning that the operation failed.
- best to leave error handling at final .catch statement
  - terminating with a throw = rejected state
- Promise.all()
  - Wait for all promises to be resolved, or for any to be rejected.
  - If the returned promise resolves, it is resolved with an aggregating array of the values from the resolved promises, in the same order as defined in the iterable of multiple promises.
  - If it rejects, it is rejected with the reason from the first promise in the iterable that was rejected.
