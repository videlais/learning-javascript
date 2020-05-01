# Generator Functions

- [Generator Functions](#generator-functions)
  - [Reviewing Iteration](#reviewing-iteration)
    - [Iterator Protocol](#iterator-protocol)
    - [Iterable Protocol](#iterable-protocol)
    - [`function*`](#function)
    - [Using `yield`](#using-yield)

## Reviewing Iteration

In an earlier chapter, *Iterators* were discussed. In JavaScript, an *iterator* is functionality for accessing the internal properties of some object. For existing, built-in objects like **Array** and **String**, they also have their own built-in iterators, which allow them to be used with the `for...of` looping structure.

As was reviewed in a previous chapter, it is also possible to define an iterator for objects through using the `Symbol` keyword. The special `[Symbol.iterator] = function()` pattern defines an iterator for that object through using **Symbol()** and creating a unique, computed instance field.

*Generator functions* have a strong relationship to iterators in that they must follow both the *iterable protocol* and *iterator protocol*. They also, because they follow these protocols, have a unique aspect to them: their state is maintained across calls.

Until the `return` keyword is used in a generator function, their state is maintained and can be re-entered and resumed. Key to this functionality is that different parts can *yield* and return **Iterator** objects to the calling code, allowing the function to be re-entered at a later point and resumed.

### Iterator Protocol

Any object can be an *iterator*. In order to qualify, it must implement the following functionality:

- It must contain a zero-argument **next()** method.
- Its **next()** method must:
  - Return an object
  - The returned object must have:
    - *done* (boolean). If iteration is finished, *done* is `true`. Otherwise, *done* is `false`.
    - *value* (Any JavaScript value). This can be omitted when *done* is `true`.

### Iterable Protocol

The use of `[Symbol.iterator] = function()` defines an iterator function for an object following the iterator protocol. If an object has a computed property of `[Symbol.iterator]`, it is *iterable*.

As was mentioned, built-in objects like **Array** and **String** have iterators and are thus *iterable*. This is also true of any other object following the iterator protocol. They also become *iterable* if they:

1) Use `[Symbol.iterator]`
2) The defined iterator returns an **Iterator**

### `function*`

Generator functions are defined using a special syntax. After the keyword `function`, they use an asterisk, \*. This marks it as a *generator function*.

```javascript
function* generatorExample(i) {
  yield i;
  yield i + 1;
  yield i + 1;
}

let gen = generatorExample(1);

// Outputs 1
console.log( gen.next().value );
```

### Using `yield`

Generator functions return **Iterators** at any use of the keyword `yield` within them. This pauses the function and its returned properties (from the iterator protocol) of *done* and *value* can be accessed.

```javascript
function* generatorExample(i) {
  yield i;
  yield i + 1;
  yield i + 1;
}

let gen = generatorExample(1);

// Outputs 1
console.log( gen.next().value );

// Outputs 2
console.log( gen.next().value );
```

The use of the keyword `yield` updates the use of *done*, *value*, and returns control to the calling code. The property *value* will be whatever follows the keyword `yield`. This works like a "temporary return statement" within the generator function, yielding values.

```javascript
function* generatorExample(i) {
  while(i < 5) {
    yield i;
    i++;
  }
}

let gen = generatorExample(1);

let iterator = gen.next();

//Outputs
// 1
// 2
// 3
// 4
while(!iterator.done) {
  console.log( iterator.value );
  iterator = gen.next();
}
```

Once the generator function has finished (a `return` statement, either explicitly or implicitly is encountered), any future calls to its **next()** method will result in `undefined`. The function, once it finishes, no longer exists.
