Objects:
- consist of props that describe the object
  - props can be accessed via dot or bracket notation
- when there are duplicate prop names, the second overwrites the first
- spread props copies props onto new object

Inheritance & Classes:
- JS is prototype-based; objects have links to other objects (prototype)
  - russian doll analogy, until null (final link in proto chain)
 - when inherited functions are executed, the value points to the inheriting object not the proto object
 - to add props to theprototype of a function:
    functionName.prototype.foo = 'bar'
 - classes: template for creating objects; not hoisted
 
  class Rectangle{
    constructor(h, w) {
      this.height;
      this.width;
     }
    }
    
 - static: methods & props that aren't needed/replicated across instances
 - extends: creates a child class of another
 
 Destructuring:
 - allows you to assign values from arrays &/or props from objects to variables
 - creates more concise and readable code
 - variables are assigned to corresponding item in arrays
 - prop being bound = variable binding to
 
 Rest:
 - operator that should be last element in an array (no trialing commas)
 - captures all trailing items
 - when the last param of a function is rest, remaining arguments are placed in an array instance
 
 Spread:
 - opposite of rest
 - expands elements 
 - takes an array or object and spreads it's items onto a new one
 
 Function Defaults:
 - defaults for function params if no value or undefined
 
