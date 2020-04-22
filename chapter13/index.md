
### Iterators

In JavaScript ES5, moving through the entries in an array or properties of an object can potentially be complicated and require multiple lines of code. JavaScript ES6 improved this common pattern through two additional keywords used with the traditional `for()` loop: `of` and `in`. These keywords access new functionality added in JavaScript ES6: *iterators*.

#### `for... of`

In JavaScript ES5, moving through an array uses the `for()` keyword and often the creation of an additional variable like *i*, *j*, or *k* where the position of each entry in the array could be accessed through increasing the value of the variable to move forward or decreasing to move backward through the array.

```javascript
var arrayExample = [1,3,4,5];

for(var i = 0; i < arrayExample.length; i++) {
  console.log(arrayExample[i]);
}
```

In JavaScript ES6, this common pattern has been improved through *iterators*. Instead of needing to save the position of an index in the array, an additional keyword, `of`, is used to iterate through the array and use the value *at* the position, instead. For each entry in the array, the variable used is *set* to that value, bypassing the need for the position.

```javascript
let arrayExample = [1,3,4,5];

for(let entry of arrayExample) {
  console.log(entry);
}
```

#### `for... in`

When working with objects, there is no access to positions. They do not have them. To help iterate over their properties, the keyword `in` can be combined with `for()`.

```javascript
let objectExample = {
  propertyOne: 2,
  propertyTwo: 3
};

for(let entry in objectExample) {
  console.log(entry);
}
```

However, instead of returning values, like with arrays, the `for... in` pattern returns the *names of the properties themselves*. To access the *values* of the properties, the square bracket syntax can be used.

```javascript
let objectExample = {
  propertyOne: 2,
  propertyTwo: 3
};

for(let entry in objectExample) {
  console.log(objectExample[entry]);
}
```

#### Defining Iterators

The `Symbol` keyword can be used to define an iterator for any object.

Consider the following code:

```javascript
let objectExample = {
  propertyOne: 2,
  propertyTwo: 3
};
```

The use of the `for...of` pattern would be able to process each property of the **objectExample** object. The following, however, would not be.

```javascript
// Create an object literal
const objectExample = {
  // First property (an array)
  numbers: [
    1, 2, 3
  ],
  // Second property (an array)
  strings: [
    'a', 'b', 'c'
  ]
};
```

In the above code, the object has properties which are, themselves, arrays. The `for... of` iterator would not be able to process the complex data structure. It is not *iteratable*.

Like other uses of `Symbol` an object can be augmented with additional properties. One of the properties that can be added is *iterator*.

Defined iterators follow the pattern of `[Symbol.iterator] = function()` where the function must return an object literal with a property named `next()` that must, itself, return an object literal with at least two properties: *done* and *value*.

The property *value* of the *next()* function is what is returned for the current loop. The property *done* is a Boolean value that marks if the loop is finished or not.

```javascript
// Create an object literal
const objectExample = {
  // First property (an array)
  numbers: [
    1, 2, 3
  ],
  // Second property (an array)
  strings: [
    'a', 'b', 'c'
  ]
};

// An iterator must return a next():
// - next() (function for values in-between start and end)
//   - Must return an object with two properties:
//     - done, if the iterating is done or not
//     - value, the current value
//
// Other data can be passed "through" the loop: other values
//  can also be returned.
//
// This example uses 'position' and updates it per loop.
objectExample[Symbol.iterator] = function() {

  // Convert object into array
  // (Used to get the total number of properties.)
  let properties = Object.keys(this);
  // Save position per loop
  let position = 0;
  // Current object
  let currentObject = this;

  return {
    // Send the object into future loops
    currentObject: currentObject,
    // Send the position into future loops
    position,
    // Define a function to get values per loop
    next() {
      // If there are no more properties,
      //  stop the loop
      if (position < properties.length) {

        // Create a value
        let value = "";
        // Save the current outer property name
        let outerEntry = properties[position];
        // Use the outer property to get the inner property name
        let innerEntry = currentObject[outerEntry];

        // Loop through the inner properties
        for(let entry of innerEntry) {
          // For each add "Internal array value:" per each
          value += "Internal array value: " +
            entry +
            "\n";
        }

        // Return the current loop
        // - done: if the loop is over
        // - value: current value in loop
        let currentPosition = {
          done: false,
          value: value
        };

        // Increase position
        position++;

        // Return current (done, value) per loop
        return currentPosition;

      } else {

        // Loop is over, set done to true
        return { done: true };

      }
    }
  };
};

// Will display the following:
//  Internal array value: 1
//  Internal array value: 2
//  Internal array value: 3
//
//  Internal array value: a
//  Internal array value: b
//  Internal array value: c
for(let entry of objectExample) {
  console.log(entry);
}
```

In the above code, an object literal is created with two properties, *numbers* and *strings*. These are arrays that hold, for *numbers*, numbers and, for *string*, a series of String values.

The iterator function first converts the object into an array, saves the position, and the current object. Each loop, within the *next()* function, the position is used to get the current outer property value. This is used to access the internal property (array values) and add a string value, "Internal array value: " in front of each.
