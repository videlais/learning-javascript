
### Default Parameters

In JavaScript ES5, it was often necessary to define the "default" values within functions and then test what was passed to it. (When not given a value, JavaScript defaults a parameter to the value of `undefined`.)

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

With multiple parameters, this approach requires lots of extra lines of code! To fix this common pattern, JavaScript ES6 added *default parameters*. These can be written inside of the parentheses of the function's definition.

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
