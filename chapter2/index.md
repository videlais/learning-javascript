# Functions

### Arrow Functions

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

#### Arrow Function Expressions

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
