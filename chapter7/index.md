
### Destructing Assignment

Often, only a few properties or the first couple of positions of an array are needed. To help with those use cases, JavaScript ES6 also adds "destructing" functionality as part of assignment operations.

In JavaScript ES5, it was possible to assign the value of an object's property in the following manner:

```javascript
let exampleObject = {
  someProperty: 5
};


let someValue = exampleObject.someProperty;
```

However, where this same operation occurs most frequently is not in the above use case, but a more common one in Node.js: *require()*-ing in an object exported by another file.

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

In the above example, only the property *oneProperty* was *require()*'d into the file. Everything else was ignored. What was previously the object **example** became an object through which the property *oneProperty* was destructed.

This functionality also works on arrays, too. Like with objects where the use of the curly brackets marks the object, it is also possible to use square brackets and give names matching the position of values within an array to destruct it.

```javascript
// Destruct an array
let [one, two] = [5, 6, 7];
// Print the value 6
console.log(two);
```
