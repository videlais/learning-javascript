# Destructing Assignment, Spread Operator, and Default Parameters

- [Destructing Assignment, Spread Operator, and Default Parameters](#destructing-assignment-spread-operator-and-default-parameters)
  - [Destructing Assignment](#destructing-assignment)
  - [Spread Operator](#spread-operator)
  - [Default Parameters](#default-parameters)

## Destructing Assignment

Often, only a few properties or the first couple of positions of an array are needed. To help with those use cases, JavaScript ES6 also adds "destructing" functionality as part of assignment operations.

In JavaScript ES5, it was possible to assign the value of an object's property in the following manner:

```javascript
let exampleObject = {
  someProperty: 5
};


let someValue = exampleObject.someProperty;
```

However, where this same operation occurs most frequently is not in the above use case, but a more common one in Node.js: **require()**-ing in an object exported by another file.

**Example.js:**

```javascript
module.exports = {
  oneProperty: 1,
  twoProperty: 2,
  threeProperty: 3
};
```

**index.js:**

```javascript
let example = require('./Example.js');

let someValue = example.oneProperty;
```

Instead of pulling in additional properties not needed or used in the file, the assignment operation can be paired with the ability to 'destruct' an object.

**Example.js:**

```javascript
module.exports = {
  oneProperty: 1,
  twoProperty: 2,
  threeProperty: 3
};
```

**index.js:**

```javascript
let { oneProperty } = require('./Example.js');

let someValue = oneProperty;
```

In the above example, only the property *oneProperty* was **require()**'d into the file. Everything else was ignored. What was previously the object **example** became an object through which the property *oneProperty* was destructed.

This functionality also works on arrays, too.

Like with objects where the use of the curly brackets marks the object, it is also possible to use square brackets and give names matching the position of values within an array to destruct it.

```javascript
// Destruct an array
let [one, two] = [5, 6, 7];
// Print the value 6
console.log(two);
```

In the above example, the variables *one* and *two* would be created and given the values of the first (0) and second (1) position values from the array.

## Spread Operator

In JavaScript ES5, either a `for()` loop or some other functionality was needed to use the entire contents of an array.

In ES6, an additional operator, `...`, the spread operator, was added for these cases. Used in front of an array, it "spreads" its contents.

```javascript
// Create an array
let arrayExample = [1,2,3,4,5,6,7,8,9,10];
// Use the spread operator to print
//  the entire contents.
console.log(...arrayExample);
```

While not immediately obvious, the spread operator also works with any use of arrays. For example, arrays can be quickly concatenated together through using their spread syntax inside another array.

```javascript
const oneArray = [1,2];
const twoArray = [3,4];

const thirdArray = [...oneArray, ...twoArray];

// Outputs [1,2,3,4]
console.log(thirdArray);
```

This also works with single values. Instead of using **unshift()** or **push()**, the spread operator can be used to add values to the front or back of an array easily.

```javascript
let oneArray = [1,2];
const twoArray = 4;

oneArray = [4, ...oneArray];

console.log( oneArray );
```

## Default Parameters

In JavaScript ES5, it was often necessary to define the "default" values within functions and then test what was passed to it. (When not given a value, JavaScript defaults an parameter's value to `undefined`.)

```javascript
function example(someValue) {
  
  // Set default value
  this.someProperty = "Default";
  
  // Test if 'someValue' has a value or not
  if(typeof someValue !== 'undefined') {
    // Overwrite value
    this.someProperty = someValue;
  }

  // Output value
  console.log(this.someProperty);
  
}

// Will output "Default"
console.log(example());

// Will output "Not default"
console.log(example("Not default"));

```

With multiple arguments, this approach requires lots of extra lines of code!

To fix this common pattern, JavaScript ES6 added *default parameters*. These can be written inside of the parentheses of the function's definition.

```javascript
function example(someValue = "Default") {
  // Output value
  console.log(someValue);
  
}

// Will output "Default"
console.log(example());

// Will output "Not default"
console.log(example("Not default"));
```

As default parameters work with all functions, they can also be used with arrow functions as well.

```javascript
let arrowExample = (value = 5) => {
  console.log(value);
}

// Outputs 5
arrowExample();

// Outputs 7
arrowExample(7);
```
