## React CustomHooks
### https://reactjs.org/docs/hooks-custom.html
- custom  hooks let you extract component logic into reusable functions
- use cases like form handling, animation, declarative subscriptions, timers, etc
  - = JavaScript functions whose name starts with ”use” and that may call other Hooks
  - only call other Hooks unconditionally at the top level of your custom Hook
  - every time you use a custom Hook, all state and effects inside of it are fully isolated (each call = isolated state)
- b/c Hooks are functions, we can pass information between them as arguments

## Rules
### https://reactjs.org/docs/hooks-rules.html
- two rules need to follow
  - linter plugin to enforce ``eslint-plugin-react-hooks``
  - included in create-react-app
  1. Only Call Hooks at the Top Level
    - Don’t call Hooks inside loops, conditions, or nested functions
      - If we want to run an effect conditionally, we can put that condition inside our Hook
    - ensures that Hooks are called in the same order each time a component renders 
  2. Only Call Hooks from React Functions
    - Call Hooks from React function components
    - Call Hooks from custom Hooks
      - ensures that all stateful logic in a component is clearly visible from its source code
 
## Custom Hooks Guide
### https://www.telerik.com/kendo-react-ui/react-hooks-guide/#toc-custom-react-hooks
- useEffectL tells React that our component needs to do something after the component render
  - runs after the first render and after every update
  - can be used with cleanup or without
    - without cleanup: you can return a function from useEffect
      - allows you to run some code after your effect and before any new effect runs
    - with cleanup: React cleans up effects from the previous render before running the effects of the next render
      - can optimize performance by skipping effects with an optional argument
      
## React Hooks Toolbox
### https://blog.bitsrc.io/10-react-custom-hooks-you-should-have-in-your-toolbox-aa27d3f5564d
- bookmarked

## Context
### https://reactjs.org/docs/context.html
- Context provides a way to pass data through the component tree without having to pass props down manually at every level - YAY!
  - for 'global' data like authenticated user, theeme, etc
  - used when some data needs to be accessible by many components at different nesting levels
    - downside: it makes component reuse more difficult
  - create context with default value ``const MyContext = React.createContext(defaultValue);`` => ``const ThemeContext = React.createContext('light');``
    - creates a Context object
  - change value on components that need it ``<MyContext.Provider value={/* some value */}>`` => ``<ThemeContext.Provider value="dark">``
    - defaultValue argument is only used when a component does not have a matching Provider above it in the tree
    - One Provider can be connected to many consumers
      - All consumers that are descendants of a Provider will re-render whenever the Provider’s value prop changes
    - Providers can be nested to override values deeper within the tree
  - Assign a contextType to read the current theme context:
```
  // React will find the closest theme Provider above and use its value.
  // In this example, the current theme is "dark".
  static contextType = ThemeContext;
  render() {
    return <Button theme={this.context} />;
  }
  ```
- another solution w/o context = pass down the component that needs props itself so that the intermediate components don’t need to know about it's props
  - inversion of control can make cleaner code by reducing the amount of props needed to pass through app and gives more control to the root components
    - downside: moving more complexity higher in the tree makes those higher-level components more complicated and forces the lower-level components to be more flexible 
