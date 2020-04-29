# Functions

- [Functions](#functions)
  - [Defining Functions](#defining-functions)
    - [Calling Functions](#calling-functions)
    - [Function Anatomy](#function-anatomy)
  - [Anonymous Functions](#anonymous-functions)
  - [Callback Functions](#callback-functions)
  - [Functions as Objects](#functions-as-objects)
    - [Function Properties](#function-properties)
      - [Function *length*](#function-length)
      - [Function *name*](#function-name)
    - [`this`](#this)
    - [Function Methods](#function-methods)
      - [Function *toString()*](#function-tostring)
      - [Function *call()*](#function-call)
      - [Function *apply()*](#function-apply)
      - [Function *bind()*](#function-bind)
  - [Arrow Functions](#arrow-functions)
  - [Arrow Function Expressions](#arrow-function-expressions)

## Defining Functions

Beyond variables, *functions* are the next most important concept to understand in programming. They allow a large, potentially complex program to be broken up and having each part perform a specific task.

Some definitions of *function* include the words procedure or routine. These are both useful words in helping to define a function in relate to other parts of code. Put simply: a function is a series of statements.

Usually, these are tied to a specific task, but this is not a rule for functions. They can be *any* series of statements that better helps organize a program or large collection of code.

### Calling Functions

In programming terminology, functions are described in relation to two terms: definition and calling.

A function is *defined* where it first appears and often in connection to the keyword `function`. This *defines* the function and how it will later be used.

When a function is used, it is *called*. This is a special operation in programming and it means including the open and closing parentheses behind the name of a function. This is also where values are passed into a function and, should it return anything, how its output is also used.

### Function Anatomy

In their most traditional form, functions are defined using the keyword `function` in JavaScript.

```javascript
function exampleFunction() {

}
```

Including their name, like for the above *exampleFunction()*, functions have multiple parts in JavaScript.

- *Name* (Optional): What the function is named.
- *Arguments:* Values passed into the function
- *Body:* What statements are inside the function
- `return` statement (Optional): What, if anything, is output from the function.

If functions are thought of as a series of statements toward a specific task, it can help to give them value to work on and then expect some form of output. Consider an example of a function called *addXandY()*.

```javascript
function addXandY(x, y) {
  return x + y;
}
```

In the above example, its different parts would be broken down as the following:

- Name: *addXandY()*
- Arguments: *x* and *y*
- Body: `return` x + y
- `return`: x + y

The function accepts two arguments, *x* and *y*, and its body is a single line.

It also has a `return` statement where its output is returned.

## Anonymous Functions

In JavaScript, functions are a type of *value*. A variable can store a function as if it were any other data type because, in JavaScript, it is!

```javascript
let exampleFunction = function() {

}
```

In the above code, the function stored in the variable *exampleFunction* does not have a name. It is an example of an *anonymous* function.

In JavaScript, anonymous functions are common. Because they they can be written using the `function` keyword and are functions, they allow for writing some parts of code that run to complete some small task or as part of other functions that call them.

## Callback Functions

When a function is *called* as part of another, it is called a *callback function*. While not a special type of function, it is a common pattern within JavaScript and much of built-in functions.

For example, the function *forEach()* as part of Array objects accepts a *callback function*. This is a function that will be called for each entry in the array. It will also be passed two values, the entry and the current position.

```javascript
let arrayExample = [1,2,3];

arrayExample.forEach(
  function(entry, position) {
    console.log(entry, position);
  }
);
```

In the above code, an anonymous function is used within the built-in function of *forEach()*. This is its *callback function*. It will be called for each entry in the array and passed, in order, its values and the position of the entry each time.

## Functions as Objects

Functions are special in JavaScript. While often designed to carry out a specific task, they are also *objects*.

When a function is defined, it is also given some built-in *properties* and *methods* as part of being an object in JavaScript.

**Note:** Objects are covered more in-depth in Chapter 3.

### Function Properties

Every function has access to two properties: *length* and *name*.

#### Function *length*

The property *length* of a function has the value of the number of arguments passed to the function.

```javascript
function exampleFunction(argument1, argument2 ,argument3) {};

// Outputs "3"
console.log(exampleFunction.length);
```

#### Function *name*

The property *name* of a function has the value of the name of the function or the name of a variable with its value if it does not have a name itself.

```javascript
function exampleFunction() {};

// Outputs "exampleFunction"
console.log(exampleFunction.name);
```

```javascript
let differentName = function() {};

// Outputs "differentName"
console.log(differentName.name);
```

If an anonymous function is used, it uses the name of the variable holding its value, instead. In the above code, for example, the output would be "differentName", the name of the variable holding the value of the anonymous function.

### `this`

All functions have access to a special keyword in JavaScript: `this`.

The keyword is possible through a useful fact to remember about functions in JavaScript: they are also objects!

```javascript
function exampleFunction() {
  this.internalValue = 5;
  return this.internalValue;
}

// Outputs 5
console.log(exampleFunction());
```

In the above code, the variable *internalValue* is a property of the function *exampleFunction()*. This means that it is accessed through the function. It is *internal* to the function.

Inside the function, there is a need to decided between a variable that might appear outside of it and the ones that are internal to it. To help be more specific, the keyword `this` is used. It means "this object."

When used with a property, a period, `.`, is used to mark its access path. For example, it starts with `this` (this object) and then extends to *its* properties, of which *internalValue* is one.

### Function Methods

When discussing objects, the internal functions to that object are often called its *methods*.

All functions have access to the following methods:

#### Function *toString()*

Returns the string source of the function.

```javascript
function exampleFunction(x, y) {
  return x + y;
};

// Outputs:
// function exampleFunction(x, y) {
//  return x + y;
//};
console.log(exampleFunction.toString());
```

#### Function *call()*

Calls the function and changes its `this` to the one supplied. Accepts any comma-separated values as additional arguments.

```javascript
function exampleFunction(argument1, argument2, argument3) {
  this.property1 = argument1;
  this.property2 = argument2;
  this.property3 = argument3;
};

function secondExampleFunction() {
  exampleFunction.call( this, 1, 2, 3 );
  console.log( this.property1 );
  console.log( this.property2 );
  console.log( this.property3 );
}

secondExampleFunction();
```

In the above example, the function *exampleFunction()* is called from inside the function *secondExampleFunction()*. It passes its own `this` to *exampleFunction()*. New properties are added, and the function returns. Inside *secondExampleFunction()*, these properties are then output.

#### Function *apply()*

Calls the function and changes its `this` to the one supplied. Accepts all additional arguments as an array value.

**Note** *apply()* and *call()* are very similar. *apply()*, however, accepts an optional array whereas *call()* accepts a list.

```javascript
function exampleFunction(argument1, argument2, argument3) {
  this.property1 = argument1;
  this.property2 = argument2;
  this.property3 = argument3;
};

function secondExampleFunction() {
  exampleFunction.apply( this, [1,2,3] );
  console.log( this.property1 );
  console.log( this.property2 );
  console.log( this.property3 );
}

secondExampleFunction();
```

#### Function *bind()*

Creates a new function with a changed `this` to the one supplied. Accepts any comma-separated values as additional arguments.

```javascript
function exampleFunction(argument1, argument2, argument3) {
  this.property1 = argument1;
  this.property2 = argument2;
  this.property3 = argument3;
};

function secondExampleFunction() {
  
  let functionValue = exampleFunction.bind( this, 1, 2, 3 );

  functionValue();

  console.log( this.property1 );
  console.log( this.property2 );
  console.log( this.property3 );
}

secondExampleFunction();
```

In the above example, the use of *bind()* creates a new function, *functionValue()*, that is then called. As its `this` is the sme as *secondExampleFunction()*, this adds the properties found in *exampleFunction()* and returns. This allows the properties to be output in the lines that follow *functionValue()*.

## Arrow Functions

In JavaScript ES5, it was often common to use an anonymous function as part of different built-in functionality in JavaScript as previous examples have shown.

```javascript
let arrayExample = [1,2,3,4];

arrayExample.forEach(function(entry, index) {
  console.log("Value: " + entry + "  Position: " + index);
});
```

However, the use of the anonymous function would also create a new function scope and an internal use of the `this` keyword local to that function.

Because this can easily create confusion about which `this` an anonymous function is trying to access -- its own or the one inside the function being used? -- a different type of function was introduced: an arrow function.

The term "arrow function" is named that way because it uses the equal sign, `=`, and the greater-then sign, `>`, together to create an 'arrow': `=>`. The 'arrow' points toward the body of the function.

To solve the issue around confusing usages of `this`, arrow functions have a unique feature of functions: their `this` is defined when they are, not where they are used.

For example, consider the following code combining different functions:

```javascript
function returnLastEntry(arrayExample) {

    this.lastValue = null;

    arrayExample.forEach( (entry, value) => {
        this.lastValue = entry;
    });

    return this.lastValue;
}
```

In the above code, the use of the arrow function allows the code inside it to access the `this` of the function it is defined within, *returnLastEntry()*. While a silly example, it shows how an arrow function can access the `this` where it is defined.

## Arrow Function Expressions

Arrow functions can use the normal syntax of functions like the following where at least one statement would be used inside the body of the function:

```javascript
() => {}
```

They can also be used as part of *arrow function expressions* in a more compact form where, instead of curly brackets, they can contain a single expression that is assumed to be run and returned without explicitly using the `return` keyword.

```javascript
() => ()
```

In fact, in these cases, the initial parentheses can even be dropped when only one value will be passed to the function, which becomes the following:

```javascript
variable => ()
```

For example, consider the following code:

```javascript
const animals = [
  'cat',
  'dog'
];

console.log(animals.map(animal => animal.length));
```
