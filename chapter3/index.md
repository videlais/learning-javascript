# Reviewing Objects

- [Reviewing Objects](#reviewing-objects)
  - [Introducing Objects](#introducing-objects)
  - [Built-in Objects](#built-in-objects)
    - [Strings](#strings)
      - [String Properties](#string-properties)
      - [String Methods](#string-methods)
      - [Concatenation](#concatenation)
    - [Arrays](#arrays)
      - [Array Properties](#array-properties)
      - [Array Methods](#array-methods)
      - [Ordered Entries](#ordered-entries)
      - [Using Loops to Access Entries](#using-loops-to-access-entries)
    - [Object Literals](#object-literals)
      - [Object Properties](#object-properties)
      - [Object Methods](#object-methods)
  - [Functions as Objects](#functions-as-objects)
    - [ES5 Objects](#es5-objects)
    - [Working with `this`](#working-with-this)
    - [Prototypes](#prototypes)
  - [Classes](#classes)
    - [Creating `new` Objects](#creating-new-objects)
    - [`class` and `extends`](#class-and-extends)
      - [`class`](#class)
      - [*constructor()*](#constructor)
        - [Class Scope](#class-scope)
      - [*super()*](#super)

## Introducing Objects

There is often a need to create or use more complex data structures. Beyond simply numbers or strings values, JavaScript provides a concept to help with this: *objects*.

In their most basic form, an object is defined through its two internal parts:

- *Properties*: Values accessed via the object or internal to it.
- *Methods*: Functions created, used, or defined in reference to the object.

In JavaScript, objects are the *building-blocks* of understanding complex data structures and using advanced functionality. Built-in objects such as **String** and **Array** are used through the properties and methods created with those types of values.

## Built-in Objects

TODO

### Strings

#### String Properties

#### String Methods

#### Concatenation

While Numbers can be added together, String values have a different special operation associated with them: *concatenation*.

This operation, *concatenation*, literally means "to put together."

With the addition symbol is used with String values, they are combined!

```javascript
let stringExample = "Hello";
stringExample = stringExample + ", world!";
```

### Arrays

#### Array Properties

#### Array Methods

Arrays are a special type of object where the order of the entries is important. They are created through using either an opening and closing square bracket together, `[]`, or using the **Array()** constructor.

#### Ordered Entries

The use of square brackets is important for arrays. Not only are they defined through using a literal list of entries with them, but entries are also accessed using their position.

```javascript
let arrayExample = [1,2,"hello"];
```

Arrays start at position 0 in JavaScript. Therefore, to access to the first (0) position of an array, the position would be given in square brackets: `[0]`.

As entries are referenced using the name of the array, to access the second (1) entry in the variable *arrayExample*, it would be the following:

```javascript
arrayExample[1] = 5;
```

Values can both be accessed and set using their position. As with the above example, the value at the second (1) position would be overwritten.

#### Using Loops to Access Entries

One of the most common ways to access all the entries of an array is using a looping keyword like `for()` or `while()`. Through using a computer position, all entries would be accessed in turn.

```javascript
let arrayExample = [1,2,"Hello"];

for(let i = 0; i < arrayExample.length; i+++) {
  arrayExample[i] = 5;
}

```

In the above code, the value 5 would be set to each existing entry, using the computer property each time through the loop.

The code example also shows an important reminder. As a type of object, all objects have some built-in properties. For arrays, they all have a *length* that is updated as values are added or removed from the array. It will always have the exact number of entries in the array.

Using the `while()` keyword would be very similar. Using a counter, a number could be checked like in the `for()` example.

```javascript
let arrayExample = [1,2,"Hello"];
let position = 0;

while (position < arrayExample.length) {
  arrayExample[position] = 5;
  position = position + 1;
}
```

### Object Literals

#### Object Properties

#### Object Methods

## Functions as Objects

### ES5 Objects

```javascript
function exampleFunction() {
  this.internalValue = 5;
  return this.internalValue;
}

var test = new exampleFunction();

console.log(test.internalValue);
```

### Working with `this`

When discussing objects, the internal functions to that object are often called its *methods*.

### Prototypes

## Classes

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
