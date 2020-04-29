# Reviewing Objects

- [Reviewing Objects](#reviewing-objects)
  - [Introducing Objects](#introducing-objects)
  - [Built-in Objects](#built-in-objects)
    - [Array](#array)
      - [Array Properties](#array-properties)
        - [Array *length*](#array-length)
      - [Ordered Entries](#ordered-entries)
      - [Using Loops to Access Entries](#using-loops-to-access-entries)
      - [Array Methods](#array-methods)
        - [Array *copyWithin()*](#array-copywithin)
        - [Array *fill(value, begin, end)*](#array-fillvalue-begin-end)
        - [Array *pop()*](#array-pop)
        - [Array *push(value, value...)*](#array-pushvalue-value)
        - [Array *reverse()*](#array-reverse)
        - [Array *shift()*](#array-shift)
        - [Array *sort()*](#array-sort)
        - [Array *splice(start[, deleteCount[, item1[, item2[, ...]]]])*](#array-splicestart-deletecount-item1-item2)
        - [Array *unshift()*](#array-unshift)
    - [Strings](#strings)
      - [String Properties](#string-properties)
        - [String *length*](#string-length)
      - [String Methods](#string-methods)
        - [String *charAt(index)*](#string-charatindex)
        - [String *concat()*](#string-concat)
        - [String *includes(value)*](#string-includesvalue)
        - [String *endsWith(value)*](#string-endswithvalue)
        - [String *indexOf(value)*](#string-indexofvalue)
        - [String *lastIndexOf(value)*](#string-lastindexofvalue)
        - [String *match()*](#string-match)
        - [String *matchAll()*](#string-matchall)
        - [String *padEnd(length, value)*](#string-padendlength-value)
        - [String *padStart(length, value)*](#string-padstartlength-value)
        - [String *repeat(number)*](#string-repeatnumber)
        - [String *replace(search, replace)*](#string-replacesearch-replace)
        - [String *search(regExp)*](#string-searchregexp)
        - [String *slice(position, end)*](#string-sliceposition-end)
        - [String *split(value)*](#string-splitvalue)
        - [String *startsWith(value)*](#string-startswithvalue)
        - [String *substring(position, end)*](#string-substringposition-end)
        - [String *toLowerCase()*](#string-tolowercase)
        - [String *toUpperCase()*](#string-touppercase)
        - [String *trim()*](#string-trim)
        - [String *trimStart()* / *trimLeft()*](#string-trimstart--trimleft)
        - [String *trimEnd()* / *trimRight()*](#string-trimend--trimright)
      - [Concatenation](#concatenation)
      - [Template Literals](#template-literals)
    - [Object Literals](#object-literals)
      - [Object Methods](#object-methods)
        - [Object *hasOwnProperty(value)*](#object-hasownpropertyvalue)
        - [Object *toString()*](#object-tostring)

## Introducing Objects

There is often a need to create or use more complex data structures. Beyond simply numbers or strings values, JavaScript provides a concept to help with this: *objects*.

In their most basic form, an object is defined through its two internal parts:

- *Properties*: Values accessed via the object or internal to it.
- *Methods*: Functions created, used, or defined in reference to the object.

In JavaScript, objects are the *building-blocks* of understanding complex data structures and using advanced functionality. Built-in objects such as **String** and **Array** are used through the properties and methods created with those types of values.

## Built-in Objects

JavaScript has several built-in objects for working with certain types of data. Notable among these, and fundamental parts of other, more complex data structures, are **Array** and **String**.

### Array

In programming terminology, an *array* is a sequence of values. In JavaScript, arrays are created and accessed through the use of opening and closing square brackets. They are also a special type of object where the order of the entries is important. They are stored *in order*.

```javascript
let arrayExample = [1,2,3];
```

Values in an array are separated by commas and enclosed in opening and square brackets.

In JavaScript, arrays are also *objects*. This means they have built-in properties and methods.

#### Array Properties

##### Array *length*

The *length* of an array is the number of entries within it. This is automatically updated.

#### Ordered Entries

The use of square brackets is important for arrays. Not only are they defined through using a literal list of entries with them, but entries are also accessed using their position.

```javascript
let arrayExample = [1,2,"hello"];
```

Arrays start at position 0 in JavaScript. Therefore, to access to the first (0) position of an array, the position would be given in square brackets: `[0]`.

As entries are referenced using the name of the array, to access the second (1) entry in the variable *arrayExample*, it would be the following:

```javascript
arrayExample[1] = 5;
```

Values can both be accessed and set using their position. As with the above example, the value at the second (1) position would be overwritten.

#### Using Loops to Access Entries

One of the most common ways to access all the entries of an array is using a looping keyword like `for()` or `while()`. Through using a computer position, all entries would be accessed in turn.

```javascript
let arrayExample = [1,2,"Hello"];

for(let i = 0; i < arrayExample.length; i+++) {
  arrayExample[i] = 5;
}

```

In the above code, the value 5 would be set to each existing entry, using the computer property each time through the loop.

The code example also shows an important reminder. As a type of object, all objects have some built-in properties. For arrays, they all have a *length* that is updated as values are added or removed from the array. It will always have the exact number of entries in the array.

Using the `while()` keyword would be very similar. Using a counter, a number could be checked like in the `for()` example.

```javascript
let arrayExample = [1,2,"Hello"];
let position = 0;

while (position < arrayExample.length) {
  arrayExample[position] = 5;
  position = position + 1;
}
```

#### Array Methods

##### Array *copyWithin()*

Copies part of an array into another part of the array.

##### Array *fill(value, begin, end)*

Fills an array with *value* from position *begin* to *end*. If *begin* and *end* are not included, fills array from beginning to end.

##### Array *pop()*

Removes the last element in the array and returns it.

##### Array *push(value, value...)*

Adds one or more values to an array and returns the new length.

##### Array *reverse()*

Reverses the positions of values in an array.

##### Array *shift()*

Removes the first element and returns it.

##### Array *sort()*

Sorts the elements of the array in place based on converting their values into strings and placing the values in ascending order.

##### Array *splice(start[, deleteCount[, item1[, item2[, ...]]]])*

Removes, replaces, or adds elements to an array in place.

##### Array *unshift()*

Add one or more elements to the front of an array and returns the new length.

### Strings

As mentioned in Chapter 1, a String is a collection of letters, numbers, and other symbol set off by single or double-quotation marks.

In programming terminology, each individual entry in a string is called a *character*. This is a single letter, number, or symbol *within* a string value.

A string is *empty* if it contains no *characters* between the quotation marks. An *empty string* is a string with characters.

In JavaScript, all string values are also a type of object: **String**.

As with all objects, all values that are object have both properties and methods.

#### String Properties

##### String *length*

All **String** values have a length. This is the number of characters in the string. It is automatically updated as characters are added or removed from the string.

```javascript
let stringExample = "Hello!";

// Outputs 6
console.log(stringExample.length);
```

#### String Methods

As strings are potentially complex or a long series of characters, there are many methods available within JavaScript for working with string values.

##### String *charAt(index)*

The function *charAt()* returns the character at the specific *index* f *index* is less than the total *length*.

If *index* is greater than the *length* of the string, it returns an empty string.

Otherwise, it returns the first position (0) within the string.

##### String *concat()*

Returns a new string value made up of all of the arguments passed combined together.

##### String *includes(value)*

Searches a string for a value, *value*. If found, the function returns `true`. Otherwise, it returns `false`.

##### String *endsWith(value)*

Returns `true` if a string ends with *value*. Otherwise, returns `false`.

##### String *indexOf(value)*

Returns the first position of *value* within the string or -1 if it cannot be found.

##### String *lastIndexOf(value)*

Returns the first position of the *last* occurrence of *value* within a string or -1 if *value* is not found in the string.

##### String *match()*

Searches a string using a Regular Expression, returning the result.

##### String *matchAll()*

Returns all capture groups based on a Regular Expression value.

##### String *padEnd(length, value)*

Returns a new string of length *length* with *value* added to the end of the current string to create a string of *length*.

##### String *padStart(length, value)*

Returns a new string of length *length* with *value* added to the beginning of the current string to create a string of *length*.

##### String *repeat(number)*

Returns a new string created through repeating the current characters *number* of times.

##### String *replace(search, replace)*

Searches for *search* within a string. If found, replaces it with *replace*. Returns a new string.

##### String *search(regExp)*

Searches a string based on a Regular Expression.

##### String *slice(position, end)*

Returns a new string from the existing string starting with *position* and ending either at the end of the string or at the position *end*.

##### String *split(value)*

Creates an array through dividing up a string based on *value*.

##### String *startsWith(value)*

Returns `true` if string begins with *value*. Otherwise, it returns `false`.

##### String *substring(position, end)*

Returns a new string starting at *position* and ending in *end*. If *end* is greater than the *length*, it returns up to the end.

##### String *toLowerCase()*

Returns the current string with all letters in lower case.

##### String *toUpperCase()*

Returns the current string with all letters in upper case.

##### String *trim()*

Returns a new string with whitespace (space, tab, no-break space) removes from the beginning and end.

##### String *trimStart()* / *trimLeft()*

Removed whitespace space, tab, no-break space) from the beginning of the string.

##### String *trimEnd()* / *trimRight()*

Removed whitespace space, tab, no-break space) from the end of the string.

#### Concatenation

While Numbers can be added together, String values have a different special operation associated with them: *concatenation*.

This operation, *concatenation*, literally means "to put together."

With the addition symbol is used with String values, they are combined!

```javascript
let stringExample = "Hello";
stringExample = stringExample + ", world!";
```

#### Template Literals

Concatenating strings is a common activity in JavaScript. To help clean up code, ES6 added new functionality: template literals.

In JavaScript ES5, adding the value of a variable to a complex string required multiple concatenation actions.

```javascript
let example = 5;
console.log('This uses a template literal: ' + example + '!');
```

In JavaScript ES6, template literals are enclosed in back-ticks, `` ` ``. Any use of a variable starts with the dollar-sign, `$`, and then is enclosed in opening and closing curly brackets.

```javascript
let example = 5;
console.log(`This uses a template literal: ${example}!`);
```

No concatenation is needed. The template literal handles all of the work to combine the value of the variable with the string around it.

### Object Literals

Beyond the build-in objects like Functions, Arrays, and String, it is also possible to create an object using open and closing curly brackets in JavaScript.

Through including the properties or methods as comma-separated values, it is possible to *literally* give an object different parts. When written in this way, it is called an *object literal*.

```javascript
let objectExample = {
  property1: 1,
  property2: 2
};
```

Property names in the *object literal* form do not have quotations around them. However, any string values would have quotation marks.

Any objects created in this way, as with all other objects, have some built-in methods.

#### Object Methods

##### Object *hasOwnProperty(value)*

Returns if *value* exists as a property within the object.

```javascript
let objectExample = {
  someProperty: 1
};

// Outputs `true`
console.log(objectExample.hasOwnProperty("someProperty"));
```

##### Object *toString()*

Returns a string representing the object.

```javascript
let objectExample = {};

// Outputs [object Object]
console.log(objectExample.toString());
```

While all objects have this method, in nearly all cases, it will need to be overwritten to return something more useful than its type.

```javascript
let objectExample = {
  toString: () => {
    return "I'm an object!";
  }
};

// Outputs "I'm an object!""
console.log(objectExample.toString());
```
