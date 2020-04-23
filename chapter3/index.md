# Reviewing Objects

## Object Literals

## Classes

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



