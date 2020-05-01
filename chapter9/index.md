# Symbol

- [Symbol](#symbol)
  - [Reviewing Symbols](#reviewing-symbols)
  - [Adding Unique Identifiers](#adding-unique-identifiers)
  - [Customizing Well-Known Functionality](#customizing-well-known-functionality)
  - [`Symbol` Shorthand](#symbol-shorthand)
    - [Computed Object Literal Properties](#computed-object-literal-properties)
    - [Computed Instance Fields](#computed-instance-fields)
    - [Hidden Properties](#hidden-properties)

## Reviewing Symbols

In programming terminology, a *symbol* is a data type with a unique value or form per instance.

In JavaScript ES6, symbols are created and used with the keyword `Symbol`.

Every use of the global constructor **Symbol()** *always* creates a unique value where the following is always true:

```javascript
Symbol() !== Symbol()
```

Because of this special usage, it has two common use cases for augmenting other objects.

## Adding Unique Identifiers

The primary use case of the keyword `Symbol` is to add *unique* identifiers to other, existing objects.

```javascript
// Create an object literal
let exampleObject = {
  // Give the object a property
  name: "exampleName"
};

// Define a symbol with a description of "name"
let exampleSymbol = Symbol("name");

// Augment an existing object with a new, hidden property
// (The value of the property will be 1,
//   not "name".)
exampleObject[exampleSymbol] = 1;

// Display the value of the augmented property
console.log(exampleObject[exampleSymbol]);
```

In the above code, a Symbol is created through the constructor **Symbol()**. It was given a description, "name", and was then used to augment an existing object through using its computed value to define a new property.

**Note:** The description of a Symbol is not its value. It is what its own property *description* will be set to internally. This can be used for debugging purposes.

`Symbol` can also be used to augment existing objects created from classes as well.

```javascript
// Define a class
class Example {
  // Define a public instance field
  publicInstanceExample = 5;
}

// Create an object based on the class
let e = new Example();

// Define a symbol with a description of "name"
let exampleSymbol = Symbol("name");

// Augment an existing object with a new, hidden property
// (The value of the property will be 1,
//   not "name".)
e[exampleSymbol] = 1;

// Display the value of the augmented property
console.log(e[exampleSymbol]);
```

## Customizing Well-Known Functionality

Beyond augmenting object properties, the keyword `Symbol` can also be used with other functionality. Existing objects can be augmented to support `match`, `search`, and `replace`, for example.

```javascript
// Define a class
class Example {
  // Define a constructor
  constructor(value) {
    // Save the value passed to the constructor()
    this.value = value;
  }
  // Augment the class
  // Define a search()
  //
  // This will return the indexOf() of
  //  the internal this.value.
  //
  // (This MUST be be "called" via search()
  //  on a string through passing a
  //  new object to it with
  //  the Symbol.search used within it!)
  [Symbol.search](string) {
    return string.indexOf(this.value);
  }
}

// search() a string through sending the argument
//  of a new Example() with a string value to
//  search for the index of internally.
console.log('some text'.search(new Example('tex')));
```

**Note:** The use of `Symbol.search`, `Symbol.match`, or `Symbol.replace` must be used with the corresponding **String.prototype** functions of **search()**, **match()**, and **replace()**.

## `Symbol` Shorthand

While the `Symbol` keyword can be used within objects, there is also a shorthand that uses square brackets with field instances.

### Computed Object Literal Properties

Object literals can be augmented using the pattern of `[symbolReference]: value` inside its definition to create a computed property name and value.

```javascript
// Create an example symbol
//
// (The variable 'exampleSymbol' holds
//  a reference to the unique value. It
//  must be used to access any properties
//  created with it.)
const exampleSymbol = Symbol();

// Create an object
const person = {
  // Use the saved value
  //  from the created symbol.
  //
  // Use the shorthand
  //  of [symbolReference]: value
  [exampleSymbol]: 'Example value'
}

// Access the created property's value
//
// (This will display "Example value".)
console.log (person[exampleSymbol]);
```

### Computed Instance Fields

The square brackets shorthand also works with classes as well. It uses the pattern of `[symbolReference] = value`.

```javascript
// Create an example symbol
//
// (The variable 'exampleSymbol' holds
//  a reference to the unique value. It
//  must be used to access any properties
//  created with it.)
const exampleSymbol = Symbol();

// Create an object
class Person {
  // Use the saved value
  //  from the created symbol.
  //
  // Use the shorthand
  //  of [symbolReference] = value
  [exampleSymbol] = 'Example value';
}

// Create a new object
//
// Add a computed instance
//  field based on the
//  reference value of the created symbol.
const p = new Person();

// Access the created property's value
//
// (This will display "Example value".)
console.log (p[exampleSymbol]);
```

### Hidden Properties

Any use of `Symbol` with an object creates a "hidden" property. This means they do not appear when **Object.keys()** or **Object.getOwnPropertyNames()** is used with the object. They augment the object, but are not a true property of it.

To access all properties defined using `Symbol`, the function **Object.getOwnPropertySymbols()** can be used. This acts like **Object.getOwnPropertyNames()**, but only returns properties created using `Symbol`.
