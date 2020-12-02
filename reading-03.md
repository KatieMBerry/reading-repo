// Class Syntax & MDN Classes //

- use class as templates for creating objects, setting initial state values, as special functions
- classes can be defined by declarations or expressions
  - neither are hoisted
  - expressions use "let = class"
    - can be named or unamed
    - may have getters and setters
  - both use the constructor method which creates and initializes an object(function)
  - listed methods and constructor inside class body
    - no commas between class methods
- new object must be called with "new" keyword
- static props and/or methods within the class body are often used for utility functions and other things that don't require replication across instances
  - need to use "this" keyword
