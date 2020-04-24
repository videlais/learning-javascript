# Functions

- [Functions](#functions)
  - [Defining Functions](#defining-functions)
    - [Function Anatomy](#function-anatomy)
  - [Anonymous Functions](#anonymous-functions)
  - [Callback Functions](#callback-functions)
  - [Arrow Functions](#arrow-functions)
    - [Arrow Function Expressions](#arrow-function-expressions)

## Defining Functions

Beyond variables, *functions* are the next most important concept to understand in programming. They allow a large, potentially complex program to be broken up into parts through having each part perform a specific task.

Some definitions of *function* include the words procedure or routine. These are both useful words in helping to define a function in relate to other parts of code. Put simply: a function is a series of commands.

Usually, the commands are tied to a specific task, but this is not a rule for functions. They can be *any* series of commands that better helps organize a program or large collection of code.

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

In the above example, its different parts would breakdown as the following:

- Name: *addXandY()*
- Arguments: *x* and *y*
- Body: `return` x + y
- `return`: x + y

The function accepts two arguments, *x* and *y*, and its body is a single line.

TODO

## Anonymous Functions

## Callback Functions

## Arrow Functions

In JavaScript ES5, it was often common to use an anonymous function as part of different built-in functionality in JavaScript.

**Note:** An anonymous function is simply one without a name.

```javascript
let arrayExample = [1,2,3,4];

arrayExample.forEach(function(entry, index) {
  console.log("Value: " + entry + "  Position: " + index);
});
```

In JavaScript ES5, the use of the anonymous function would also create a new function scope and an internal use of the *this* keyword local to that function.

Because this can easily create confusion about which *this* an anonymous function is trying to access -- its own or the one inside the function being used? -- a different type of function was introduced: an arrow function.

The term "arrow function" is named that way because it uses the equal sign, `=`, and the greater-then sign, `>`, together to create an 'arrow': `=>`. The 'arrow' points toward the body of the function.

To solve the issue around confusing usages of *this*, arrow functions have a unique feature of functions: their *this* is defined when they are, not where they are used.

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

In the above code, the use of the arrow function allows the code inside it to access the *this* of the function it is defined within, *returnLastEntry()*. While a silly example, it shows how an arrow function can access the *this* where it is defined.

### Arrow Function Expressions

Arrow functions can use the normal syntax of functions like the following where at least one statement would be used inside the body of the function:

```javascript
() => {}
```

They can also be used as part of *arrow function expressions* in a more compact form where, instead of curly brackets, they can contain a single expression that is assumed to be run and returned.

```javascript
() => ()
```

In fact, in these cases, the initial parentheses can even be dropped when only one parameter will be passed to the function, which becomes the following:

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
