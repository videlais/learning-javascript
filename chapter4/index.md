# Classes

- [Classes](#classes)
  - [Extending Objects](#extending-objects)
    - [`new` Chains](#new-chains)
    - [Complications with *prototype* and `this`](#complications-with-prototype-and-this)
  - [ES6 Classes](#es6-classes)
    - [Creating `new` Objects](#creating-new-objects)
    - [`class` and `extends`](#class-and-extends)
      - [`class`](#class)
      - [*constructor()*](#constructor)
        - [Class Scope](#class-scope)
      - [*super()*](#super)

## Extending Objects

In the previous chapter, objects were reviewed as having properties and methods. Object Literals were also introduced as way to create objects based on using the opening and closing curly brackets.

Prior to ES6, all objects in JavaScript used a concept called *prototypical inheritance*. Objects were part of something called the *prototype chain*.

Every object, including the built-in objects, was given a property called *prototype* that defined what the "prototype" of each type of object had as properties and methods.

As all objects were based these prototypes, it was possible to extend an object and give it more functionality.

### `new` Chains

The use of the *prototype* property creates a new property or method of *future* objects using the same pattern. In other words, if something new is created from that pattern, the prototype "chain" connects the new object with the changed pattern with the original pattern: there is a "chain" between them.

```javascript
function functionExample() {}
functionExample.prototype.exampleProperty = 5;
```

However, as *prototype* only affects *future* objects, new objects have to be created based on the old pattern.

To create a new copy of an object, the keyword `new` is used. When paired with functions, this creates a new copy of the function, including anything internal to it (properties and methods) and anything on its *prototype*.

```javascript
function functionExample() {}

functionExample.prototype.anotherExampleProperty = 5;

let newObject = new functionExample();

// Outputs 6
console.log(newObject.anotherExampleProperty);
```

In JavaScript ES5, it was extremely common to create complex objects through adding more properties and methods to an object through writing a "blueprint" for it and then creating a `new` object based on the pattern, gaining everything on the *prototype* as they were part of the object itself.

### Complications with *prototype* and `this`

As functions are a type of object, it is possible to add properties to them. Inside a function, the `this` keyword can be used to add new properties and methods.

```javascript
function exampleFunction() {
  this.internalValue = 5;
}

var test = new exampleFunction();

console.log(test.internalValue);
```

The `this` keyword refers to "this object" and allows an function (object) to refer to itself and any properties and methods that are a part of it.

```javascript
function exampleFunction() {
  
  this.internalValue = 5;
  
  this.internalMethod = () => {
    return this.internalValue;
  };

}

var test = new exampleFunction();

// Outputs 5
console.log(test.internalMethod());
```

However, the use of `this` poses an interesting challenge as it intersects with *prototype*.

```javascript
function exampleFunction() {
  
  this.internalValue = 5;
  
  this.internalMethod = () => {
    return this.anotherValue;
  };

}

exampleFunction.prototype.anotherValue = 7;

var test = new exampleFunction();

// Outputs 7
console.log(test.internalMethod());
```

In the above code, the object **test** can access the property *anotherValue* because it is part of the prototype it gained through creating a new copy of the existing pattern of *exampleFunction()* and the property added via *prototype*.

However, if tested with *hasOwnProperty()*, the property *anotherValue* would return `false`.

```javascript
function exampleFunction() {
  
  this.internalValue = 5;
  
  this.internalMethod = () => {
    return this.anotherValue;
  };

}

exampleFunction.prototype.anotherValue = 7;

var test = new exampleFunction();

// Outputs `false`
console.log(test.hasOwnProperty("anotherValue"));
```

The property *anotherValue* is *not* a property of *exampleFunction()*. It is a property of the *prototype* of *exampleFunction()*. This may seem a technicality, but it poses complications and challenges on trying to let one object be based on previous objects.

## ES6 Classes

### Creating `new` Objects

### `class` and `extends`

Starting with ES6, JavaScript is now a true object-oriented programming language. Previous to ES6, it was possible to replicate most object-oriented programming functionality. However, ES6 added two important keywords, `class` and `extends`, that enabled full OOP support.

#### `class`

The `class` keyword is used to create classes in JavaScript. It defines a set of properties and functions that exist within the class as enclosed within curly brackets.

```javascript
class Example {

}
```

When used with the `class` keyword, `extends` enables inheritance between classes. In object-oriented programming terms, this allows one object to 'extend' an existing one through gaining everything it has and adding more.

**index.js:**

```javascript
class Example {

}

class Another extends Example {

}
```

#### *constructor()*

Classes are created through the use of the `new` keyword. This creates an object based on the class. In this way, classes are often thought of as 'blueprints' for the object to be created.

**index.js:**

```javascript
// Define the class 'Example'
class Example {
}

// Create an object based on the class 'Example'
let another = new Example();
```

In object-oriented terms, this process *constructs* a new object based on the class. In fact, JavaScript, like many other object-oriented programming languages, supplies a special function named *constructor()* for that purpose.

When the *constructor()* function is added inside a class, it is the first function called when an object is being "constructed." (If not supplied, JavaScript will automatically generate one.)

**index.js:**

```javascript
// Define the class 'Example'
class Example {
  // Create a constructor()
  constructor() {
    // Anything inside the constructor()
    //  will be called during the
    //  "construction" process.
    console.log("This will be called!");
  }
}

// Create an object based on the class
//  'Example'
let another = new Example();
```

The *constructor()* also serves an additional purpose: it allows a class to accept values during the "construction" process. Because it is a function, the *constructor()* function can also accept values.

```javascript
// Define the class 'Example'
class Example {
  // Because constructor() is a function,
  //  it can also accept values.
  constructor(value) {
    // This will show '5'
    console.log(value);
  }
}

// Create an object based on the class
//  'Example' and pass it a value, 5.
let another = new Example(5);
```

##### Class Scope

Within a class defined in JavaScript, the `this` refers to the class itself. Like with function scope, this allows a class to have properties and functions that can be accessed within itself and externally through referencing an object based on the class.

**index.js:**

```javascript
// Define the class 'Example'
class Example {
  constructor() {
    this.someValue = 5;
  }
}

// Create an object based on the class 'Example'
let another = new Example();

// This will output '5'
console.log(another.someValue);

```

#### *super()*

The use of the keyword `extends` allows one class to "extend" another. However, what if there was a need to pass values from one *constructor()* to another? JavaScript provides the function *super()* to do that.

In OOP terms, these classes exist a parent-child relationship. The first, original class is the 'parent' and the class that is extending it is the 'child'. Using the function *super()* calls the parent's *constructor()* and pass values to it.

**index.js:**

```javascript
// Define the class 'Example'
class Example {
  // Define a constructor()
  constructor(value) {
    // Print the value to the console
    console.log(value);
  }
}

// Define the class 'Another'
//  based on the class 'Example'
class Another extends Example {
  // Define a constructor()
  constructor(value) {
    // The parent's constructor()
    super(value);
  }
}

// Create an object based on 'Another'
//  (which is based on 'Example')
//
// This will print the value 5
//  because it is being passed
//  from one constructor() to another.
let another = new Another(5);
```

The keyword `super` also allows a child class to call a parent's *functions* as well. Because it has access to the parent's functions, it can call a function as if it was the parent through the keyword `super`.

```javascript
// Define the class 'Example'
class Example {
  // Define a function
  parentExample() {
    console.log("I'm the parent!");
  }

}

// Define the class 'Another'
//  based on the class 'Example'
class Another extends Example {
  // Define a constructor()
  constructor() {
    // Call the parent's constructor()
    super();
    // Call a function as if the parent
    super.parentExample();
  }
}

// Create an object based on 'Another'
//  (which is based on 'Example')
let another = new Another();
```

The one rule with using the keyword `super` in this way is that the parent's constructor must be called via *super()* before any other usages in the class. It has to be created before its functions can be called!
