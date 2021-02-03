## Architectural Styles and Architectural Patterns
- Architectural Pattern = general and reusable solution to an occurring problem in a particular context
  - purpose = to understand how major parts of the system fit together and how messages and data flow through the system
  -  diff from design patterns b/c concern large-scale components, global properties and mechanisms (not a specidic section of code)
  - examples:
     1. Layered (each focuses on one role):
        a. Presentation layer or UI layer
        b. Application layer or Service layer
        c. Business logic layer or Domain layer
        d. Data access layer or Persistence layer
     2. Event-Driven (emitters & consumers)
- Architectural Styles = name of an recurrent Architectural Design
  - examples:
     1. Domain-Driven (obj oriented)
        - understanding and interpreting the important aspects of the given problems
        - eases communication and improves flexibility
        - useful when we build complex software where the need for change is determined
     2. Pipes and Filters
        - decomposes a task that performs complex processing into a series of separate elements that can be reused
        - filters = components that transform or filter data
          - transforms the data it receives through Pipes with which it is connected. A Filter can have many input Pipes and many output Pipes
        - pipes = connectors that pass data from one filters to the next
        - pump = data source
        - sink = final target
        - can be useful when flexibility is required or when each step of the processing of the application have different scalability requirements
     3. Microservices
        - create several tiny programs
        - requires every service to be independent of others
        - helpful when want to develop new applications rapidly
- idioms = describes how to implement particular aspects of the components or the relationships between them

## Container and Presentation Pattern
### https://alchemycodelab.github.io/fsjs-notes/05_react/patterns/container_presentation/
- code is split up by:
  - containers : are stateful components that contain your business login (how things work)
    - pass information to other components via props
  - presentations : are stateless components that present your data (how things look)
    - receive props and use those props to render and style DOM
    
## Container Component Details
### https://alchemycodelab.github.io/fsjs-notes/05_react/patterns/container_presentation/container-details
- class based container components can initialize state in two ways: 
  1. class properties (cleaner)
  2. inside a constructor
- fetch data with a service function
- componentDidUpdate = if component needs to fetch data based on some user interaction, prop change, or state change 
- useState hook =  initializes state ``import React, { useState } from 'react'``
- useEffect hook = handles side effects
  - takes two arguments: 
    1. a function that preforms the side effect 
    2. an array of values that, when changed, trigger the side effect
- Containers can also be written as custom hooks

## Presentation Component Details
### https://alchemycodelab.github.io/fsjs-notes/05_react/patterns/container_presentation/presentation-details
-  written as functional components & return the markup that is going to get rendered to the DOM
- often we’ll need to pass props into our presentational components in order to make them reusable
  - use prop-types to specify the props component receives
  
## Functional vs Class-Components in React
### https://medium.com/@Zwenza/functional-vs-class-components-in-react-231e3fbd7108
- since a functional component is just a plain JavaScript function, you cannot use setState() in your component
  - if need state in component, either create a class component or lift the state up to the parent component and pass it down the functional component via props
  - can't use lifecycle hooks b/c all come from the React.Component
- benefits of functional components:
  1. easier to read and test because they are plain JavaScript functions without state or lifecycle-hooks
  2. less code
  3. best practices
  4. may be a performance boost for functional component in future React versions
  
## Conditional Rendering
### https://reactjs.org/docs/conditional-rendering.html
- works the same way conditions work in JavaScript
- can use variables to store elements
- embed expressions in JSX by wrapping them in curly braces (ex: &&)
  - if the condition is true, the element right after && will appear in the output. If it is false, React will ignore and skip it
  - If-Else with Conditional Operator 
    ```
      <div>
        The user is <b>{isLoggedIn ? 'currently' : 'not'}</b> logged in.
      </div>
    ```
- In rare cases you might want a component to hide itself even though it was rendered by another component. To do this return null instead of its render output
  - componentDidUpdate will still be called
