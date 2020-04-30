# Public, Static and Private Instance Fields

- [Public, Static and Private Instance Fields](#public-static-and-private-instance-fields)
  - [Public Instance Fields](#public-instance-fields)
    - [Private Instance Fields](#private-instance-fields)
    - [Static Class Properties and Methods](#static-class-properties-and-methods)
  - [Global Static Functions](#global-static-functions)
    - [Object Static Methods](#object-static-methods)
      - [**Object.assign(objectA, objectB)**](#objectassignobjecta-objectb)
      - [**Object.create(objectA)**](#objectcreateobjecta)
      - [**Object.defineProperty(object, property)**](#objectdefinepropertyobject-property)
      - [**Object.defineProperties(object, properties)**](#objectdefinepropertiesobject-properties)
      - [**Object.entries(objectA)**](#objectentriesobjecta)
      - [**Object.freeze(objectA)**](#objectfreezeobjecta)
      - [**Object.getOwnPropertyDescriptor(objectA, propertyB)**](#objectgetownpropertydescriptorobjecta-propertyb)
      - [**Object.getOwnPropertyDescriptors(objectA)**](#objectgetownpropertydescriptorsobjecta)
      - [**Object.getOwnPropertyNames(objectA)**](#objectgetownpropertynamesobjecta)
      - [**Object.getOwnPropertySymbols(objectA)**](#objectgetownpropertysymbolsobjecta)
      - [**Object.is(value1, value2)**](#objectisvalue1-value2)
      - [**Object.isFrozen(objectA)**](#objectisfrozenobjecta)
      - [**Object.isSealed(objectA)**](#objectissealedobjecta)
      - [**Object.keys(objectA)**](#objectkeysobjecta)
      - [**Object.seal(objectA)**](#objectsealobjecta)
      - [**Object.values(objectA)**](#objectvaluesobjecta)
    - [Math Static Methods](#math-static-methods)
      - [**Math.abs(x)**](#mathabsx)
      - [**Math.acos(x)**](#mathacosx)
      - [**Math.acosh(x)**](#mathacoshx)
      - [**Math.asin(x)**](#mathasinx)
      - [**Math.asinh(x)**](#mathasinhx)
      - [**Math.atan(x)**](#mathatanx)
      - [**Math.atanh(x)**](#mathatanhx)
      - [**Math.atan2(y, x)**](#mathatan2y-x)
      - [**Math.cbrt(x)**](#mathcbrtx)
      - [**Math.ceil(x)**](#mathceilx)
      - [**Math.clz32(x)**](#mathclz32x)
      - [**Math.cos(x)**](#mathcosx)
      - [**Math.cosh(x)**](#mathcoshx)
      - [**Math.exp(x)**](#mathexpx)
      - [**Math.expm1(x)**](#mathexpm1x)
      - [**Math.floor(x)**](#mathfloorx)
      - [**Math.fround(x)**](#mathfroundx)
      - [**Math.hypot([x[, y[, ...]]])**](#mathhypotx-y)
      - [**Math.imul(x, y)**](#mathimulx-y)
      - [**Math.log(x)**](#mathlogx)
      - [**Math.log1p(x)**](#mathlog1px)
      - [**Math.log10(x)**](#mathlog10x)
      - [**Math.log2(x)**](#mathlog2x)
      - [**Math.max([x[, y[, ...]]])**](#mathmaxx-y)
      - [**Math.min([x[, y[, ...]]])**](#mathminx-y)
      - [**Math.pow(x, y)**](#mathpowx-y)
      - [**Math.random()**](#mathrandom)
      - [**Math.round(x)**](#mathroundx)
      - [**Math.sign(x)**](#mathsignx)
      - [**Math.sin(x)**](#mathsinx)
      - [**Math.sinh(x)**](#mathsinhx)
      - [**Math.sqrt(x)**](#mathsqrtx)
      - [**Math.tan(x)**](#mathtanx)
      - [**Math.tanh(x)**](#mathtanhx)
      - [**Math.trunc(x)**](#mathtruncx)
    - [Number Static Methods](#number-static-methods)
      - [**Number.isNaN()**](#numberisnan)
      - [**Number.isFinite()**](#numberisfinite)
      - [**Number.isInteger()**](#numberisinteger)
      - [**Number.isSafeInteger()**](#numberissafeinteger)
      - [**Number.parseFloat(string)**](#numberparsefloatstring)
      - [**Number.parseInt(string, [radix])**](#numberparseintstring-radix)
    - [Console Static Methods](#console-static-methods)
      - [**console.assert(argument)**](#consoleassertargument)
      - [**console.clear()**](#consoleclear)
      - [**console.count()**](#consolecount)
      - [**console.countReset()**](#consolecountreset)
      - [**console.debug()**](#consoledebug)
      - [**console.dir()**](#consoledir)
      - [**console.dirxml()**](#consoledirxml)
      - [**console.error()**](#consoleerror)
      - [**console.group()**](#consolegroup)
      - [**console.groupCollapsed()**](#consolegroupcollapsed)
      - [**console.groupEnd()**](#consolegroupend)
      - [**console.info()**](#consoleinfo)
      - [**console.log()**](#consolelog)
      - [**console.table()**](#consoletable)
      - [**console.time()**](#consoletime)
      - [**console.timeEnd()**](#consoletimeend)
      - [**console.timeLog()**](#consoletimelog)
      - [**console.trace()**](#consoletrace)
      - [**console.warn()**](#consolewarn)
    - [JSON Static Methods](#json-static-methods)
      - [**JSON.parse(text)**](#jsonparsetext)
      - [**JSON.stringify(value[, replacer[, space]])**](#jsonstringifyvalue-replacer-space)
    - [Static Global Functions](#static-global-functions)
      - [**eval(string)**](#evalstring)
      - [**isFinite(x)**](#isfinitex)
      - [**isNaN(x)**](#isnanx)
      - [**parseFloat(x)**](#parsefloatx)
      - [**parseInt(x, radix)**](#parseintx-radix)
      - [**setInterval(callback, time)**](#setintervalcallback-time)
      - [**setTimeout(callback, time)**](#settimeoutcallback-time)
    - [**clearInterval(label)**](#clearintervallabel)

## Public Instance Fields

In JavaScript ES6, it is possible to create a *public instance field*.

What this means is that a field (a property or method) is created outside of the *constructor()* function within a class. It is *public* because it acts like a property of the class and is a *field* because it is defined outside of using the `this` keyword.

While still an experimental feature in some JavaScript contexts, many already support this ES6 feature.

```javascript
class Element {
  instanceExample = 5;
}
```

In the above code, the value of the public instance field *instanceExample* is 5. This is a property that is added *outside* of the normal usage of the **constructor()**, but is part of any instance of the class.

Instance fields can hold any value, which means they can also hold the value of a function.

```javascript
class Element {
  instanceFunction = function() {
    // Do something
  };
}
```

Holding the value of a function also means they can hold arrow functions as well. This opens the ability to have a property that is an arrow function whose `this` is the class itself.

```javascript
class Element {
  instanceArrowFunction = () => {
    // Do something
  };
}
```

In the above code, the value of the property *arrowFunctionExample* is an arrow function. Using public instance fields allows the value of a function to use the special context of arrow functions: their `this` is defined where they are, not where they are used.

Instance fields can also have computed names. It is possible to create a new property (instance field) using the same general syntax used with an object literal: square brackets around the property name.

```javascript
const fieldName = "ExampleName";

class ExampleClass {
  
  ['new' + fieldName] = 5;
  
  exampleFunction() {
    console.log(this.newExampleName);
  }

}

let e = new ExampleClass();

console.log( e.exampleFunction() );
```

In the above code, the property *newExampleName* is computed inside of the square brackets used as part of the instance field. It is computed and then added to the instance and can be used by any object based on the class.

### Private Instance Fields

Normally, all properties of a class are public in JavaScript. Their values can be accessed through their names. With private instance fields, this level of access can be changed. Values can be set to *private* so that only the class, and not even its children, can access it.

To create private instance fields, the hash symbol, `#`, can be used. It can only be used with fields and cannot be used for properties defined inside of a **constructor()** function.

```javascript
class ExampleClass {
  
  #privateValue = 6;
  
  exampleFunction() {
    console.log(this.#privateValue);
  }

}

let e = new ExampleClass();

console.log( e.exampleFunction() );
```

Often called "hash names," as they have the hash symbol in front of them, they can *only* be accessed in the class in which they appear. They cannot be inherited by child classes, and their values cannot be accessed outside the class.

### Static Class Properties and Methods

Some JavaScript environments support using the experimental keyword `static`. It can be paired with both methods and public fields in a class.

When used with a class, it changes a method from being part of an instance (object) to being part of the *class* itself. It creates a single copy across *all* instances of the class, making it "static" to the class. It also, because it is static, comes with some extra rules.

A static method:

- Can be called using the name of the class
- Can only call or reference other static methods and values
- Cannot use `this`
- Cannot use **super()**

As the method is static to the class and not any particular instance, it does not have access to `this` or **super()**. However, it can be called using the name of the class outside of any instance of the class.

```javascript
class ExampleClass {
  static staticMethod() {
    return 'Static method has been called';
  }
}

console.log( ExampleClass.staticMethod() );
```

A static public field in a class works the same as a static method: it can be used with the name of the class outside of any instance. It is "static" to the class, after all.

```javascript
class ExampleClass {

  static publicFieldExample = 5;

}

console.log( ExampleClass.publicFieldExample );

```

## Global Static Functions

Many of the built-in global objects in JavaScript have their own static methods.

### Object Static Methods

#### **Object.assign(objectA, objectB)**

Copies all of the own properties from **objectA** to **objectB**.

```javascript
const objectA = {
  property1: 1
}

const objectB = {
  property2: 2
}

let objectC = {};

Object.assign(objectC, objectA);

Object.assign(objectC, objectB);

// Outputs 1 2
console.log( objectC.property1, objectC.property2);
```

#### **Object.create(objectA)**

Create a new object using **objectA** as its prototype.

```javascript
const objectA = {
  property1: 1
}

let objectC = Object.create(objectA);

// Outputs 1
console.log( objectC.property1 );
```

#### **Object.defineProperty(object, property)**

Defines a new *property* on **object**. This is passed as an object literal, setting its accessor descriptors.

```javascript
const objectA = {
}

Object.defineProperty(
  objectA,
  "property1",
  {
    value: 42
  }
);

// Outputs 42
console.log( objectA.property1 );
```

#### **Object.defineProperties(object, properties)**

Defines multiple properties found within the object literal *properties* on the object **object**.

```javascript
const objectA = {
}

Object.defineProperties(objectA,
{
  "property1":
  {
    value: 2
  },
  "property2":
  {
    value: 4
  }
 }
);

// Outputs 2
console.log( objectA.property1 );
```

#### **Object.entries(objectA)**

Returns an array of `[key, value]` pairs for all properties of an object. (Does not access the prototype chain.)

```javascript
const objectA = {
  property1: 1,
  property2: 2
}

// Outputs
// [ [ 'property1', 1 ], [ 'property2', 2 ] ]
console.log( Object.entries(objectA) );
```

#### **Object.freeze(objectA)**

Prevents any changes to the object, its properties and methods, and includes to its prototype chain.

```javascript
let objectA = {
  property1: 1,
  property2: 2
}

Object.freeze(objectA);

objectA.property1 = 3;

// Outputs 1
console.log( objectA.property1 );
```

**Note:** **freeze()** differs from **seal()**. If an object is sealed, new properties cannot be added. If it is frozen, values cannot be changed.

#### **Object.getOwnPropertyDescriptor(objectA, propertyB)**

Returns the descriptor of *propertyB* within **objectA**.

```javascript
const objectA = {
  property1: 1,
  property2: 2
}

// Outputs
// { value: 1, writable: true, enumerable: true, configurable: true }
console.log ( Object.getOwnPropertyDescriptor(objectA, "property1") );
```

#### **Object.getOwnPropertyDescriptors(objectA)**

Returns an object containing all descriptors of the properties of the *objectA*.

```javascript
const objectA = {
  property1: 1,
  property2: 2
}

// Outputs
// {
//  property1: { value: 1, writable: true, enumerable: true, configurable: true },
//  property2: { value: 2, writable: true, enumerable: true, configurable: true }
// }
console.log ( Object.getOwnPropertyDescriptors(objectA) );
```

#### **Object.getOwnPropertyNames(objectA)**

Returns an array of all own properties of *objectA*.

```javascript
const objectA = {
  property1: 1,
  property2: 2
}

// Outputs [ 'property1', 'property2' ]
console.log( Object.getOwnPropertyNames(objectA) );
```

#### **Object.getOwnPropertySymbols(objectA)**

Returns an array of **Symbol** properties of *objectA*.

```javascript
const objectA = {
  property1: 1,
  property2: 2,
  [Symbol("property3")]: 3
}

// Output [ Symbol(property3) ]
console.log ( Object.getOwnPropertySymbols(objectA) );
```

#### **Object.is(value1, value2)**

Returns `true` if **value1** and **value2** are equal. (Does not convert values into a type and does **not** return if all of the properties of each object are also equal.)

```javascript
// Outputs true
console.log ( Object.is(null, null) );
```

#### **Object.isFrozen(objectA)**

Returns if **objectA** is frozen or not.

```javascript
let objectA = {
  property1: 1,
  property2: 2
}

Object.freeze(objectA);

// Outputs true
console.log( Object.isFrozen(objectA) );
```

#### **Object.isSealed(objectA)**

Returns if an object is sealed or not.

```javascript
let objectA = {
  property1: 1,
  property2: 2
}

Object.seal(objectA);

// Outputs true
console.log ( Object.isSealed(objectA) );
```

#### **Object.keys(objectA)**

Returns an array of the names of all of the properties of **objectA**.

```javascript
const objectA = {
  property1: 1,
  property2: 2
}

// Outputs [ 'property1', 'property2' ]
console.log( Object.keys(objectA) );
```

#### **Object.seal(objectA)**

Seals **objectA**. Prevents properties from being deleted or changed in any way.

**Note:** **seal()** differs from **freeze()**. If an object is sealed, new properties cannot be adde. If it is frozen, values cannot be changed.

```javascript
let objectA = {
  property1: 1,
  property2: 2
}

Object.seal(objectA);

objectA.property3 = 3;

// Outputs undefined
console.log ( objectA.property3 );
```

#### **Object.values(objectA)**

Returns the values of all properties of **objectA**.

### Math Static Methods

**Note:** All methods for static methods of **Math** are included for completeness. Examples are not provided.

#### **Math.abs(x)**

Returns the absolute value of a number.

#### **Math.acos(x)**

Returns the arccosine of a number.

#### **Math.acosh(x)**

Returns the hyperbolic arccosine of a number.

#### **Math.asin(x)**

Returns the arcsine of a number.

#### **Math.asinh(x)**

Returns the hyperbolic arcsine of a number.

#### **Math.atan(x)**

Returns the arctangent of a number.

#### **Math.atanh(x)**

Returns the hyperbolic arctangent of a number.

#### **Math.atan2(y, x)**

Returns the arctangent of the quotient of its arguments.

#### **Math.cbrt(x)**

Returns the cube root of a number.

#### **Math.ceil(x)**

Returns the smallest integer greater than or equal to a number

#### **Math.clz32(x)**

Returns the number of leading zeroes of a 32-bit integer.

#### **Math.cos(x)**

Returns the cosine of a number.

#### **Math.cosh(x)**

Returns the hyperbolic cosine of a number.

#### **Math.exp(x)**

Returns E^x, where x is the argument, and E is Euler's constant (2.718..., the base of the natural logarithm).

#### **Math.expm1(x)**

Returns subtracting 1 from exp(x).

#### **Math.floor(x)**

Returns the largest integer less than or equal to a number.

#### **Math.fround(x)**

Returns the nearest single precision float representation of a number.

#### **Math.hypot([x[, y[, ...]]])**

Returns the square root of the sum of squares of its arguments.

#### **Math.imul(x, y)**

Returns the result of a 32-bit integer multiplication.

#### **Math.log(x)**

Returns the natural logarithm (㏒e; also, ㏑) of a number.

#### **Math.log1p(x)**

Returns the natural logarithm (㏒e; also ㏑) of 1 + x for a number.

#### **Math.log10(x)**

Returns the base 10 logarithm of a number.

#### **Math.log2(x)**

Returns the base 2 logarithm of a number.

#### **Math.max([x[, y[, ...]]])**

Returns the largest of zero or more numbers.

#### **Math.min([x[, y[, ...]]])**

Returns the smallest of zero or more numbers.

#### **Math.pow(x, y)**

Returns base to the exponent power, that is, xy.

#### **Math.random()**

Returns a pseudo-random number between 0 and 1.

#### **Math.round(x)**

Returns the value of a number rounded to the nearest integer.

#### **Math.sign(x)**

Returns the sign of the x, indicating whether x is positive, negative, or zero.

#### **Math.sin(x)**

Returns the sine of a number.

#### **Math.sinh(x)**

Returns the hyperbolic sine of a number.

#### **Math.sqrt(x)**

Returns the positive square root of a number.

#### **Math.tan(x)**

Returns the tangent of a number.

#### **Math.tanh(x)**

Returns the hyperbolic tangent of a number.

#### **Math.trunc(x)**

Returns the integer part of the number x, removing any fractional digits.

### Number Static Methods

#### **Number.isNaN()**

Determine whether the passed value is NaN (Not a Number).

```javascript
// Outputs false
console.log ( Number.isNaN(-1) );
```

#### **Number.isFinite()**

Determine whether the passed value is a finite number.

```javascript
// Outputs true
console.log ( Number.isFinite(-1) );
```

#### **Number.isInteger()**

Determine whether the passed value is an integer.

```javascript
// Outputs true
console.log ( Number.isInteger(4) );
```

#### **Number.isSafeInteger()**

Determine whether the passed value is a safe integer.

```javascript
// Outputs true
console.log ( Number.isSafeInteger(655555555555) );
```

#### **Number.parseFloat(string)**

This is the same as the global parseFloat() function.

```javascript
// Outputs 4.56
console.log ( Number.parseFloat("4.56") );
```

#### **Number.parseInt(string, [radix])**

This is the same as the global parseInt() function.

```javascript
// Outputs 4
console.log ( Number.parseInt("4") );
```

### Console Static Methods

#### **console.assert(argument)**

Log a message and stack trace to console if the first **argument** is false.

```javascript
// Outputs "Assertion failed"
console.assert(true == false);
```

#### **console.clear()**

Clear the console.

```javascript
// Outputs "Hi!"
console.log("Hi!");
// Clears output
console.clear()
```

#### **console.count()**

Log the number of times this line has been called with the given label.

```javascript
// Outputs
// Testing: 1
// Testing: 2
console.count("Testing");
console.count("Testing")
```

#### **console.countReset()**

Resets the value of the counter with the given label.

```javascript
// Outputs
// Testing: 1
// Testing: 1
console.count("Testing");
console.countReset("Testing");
console.count("Testing");
```

#### **console.debug()**

Outputs a message to the console with the log level "debug".

```javascript
console.debug("Debug level message!");
```

#### **console.dir()**

Displays an interactive listing of the properties of a specified JavaScript object in browsers. This listing lets you use disclosure triangles to examine the contents of child objects.

```javascript
const objectExample = {
  property1: 1,
  property2: 2
}

// Outputs
// { property1: 1, property2: 2 }
console.dir( objectExample );
```

#### **console.dirxml()**

Displays an XML/HTML Element representation of the specified object if possible or the JavaScript Object view if it is not possible in browsers.

```javascript
const objectExample = {
  property1: 1,
  property2: 2
}

// Outputs
// { property1: 1, property2: 2 }
console.dirxml( objectExample );
```

#### **console.error()**

Outputs an error message. You may use string substitution and additional arguments with this method.

```javascript
console.error( "Door happened!" );
```

#### **console.group()**

Creates a new inline group, indenting all following output by another level. To move back out a level, call groupEnd().

```javascript
// Outputs
//   Part of the group!
//   Part of the group!
console.group();
console.log("Part of the group!");
console.log("Part of the group!");
console.groupEnd();
```

#### **console.groupCollapsed()**

Creates a new inline group, indenting all following output by another level. However, unlike group() this starts with the inline group collapsed requiring the use of a disclosure button to expand it in browsers. To move back out a level, call groupEnd().

```javascript
// Outputs
//   Part of the group!
//   Part of the group!
console.groupCollapsed();
console.log("Part of the group!");
console.log("Part of the group!");
console.groupEnd();
```

#### **console.groupEnd()**

Exits the current inline group.

```javascript
// Outputs
//   Part of the group!
//   Part of the group!
console.group();
console.log("Part of the group!");
console.log("Part of the group!");
console.groupEnd();
```

#### **console.info()**

Informative logging of information. You may use string substitution and additional arguments with this method.

```javascript
console.info("Info message!");
```

#### **console.log()**

For general output of logging information. You may use string substitution and additional arguments with this method.

```javascript
console.log("Hi");
```

#### **console.table()**

Displays tabular data as a table.

```javascript

// Outputs
// ┌─────────┬───────────┐
// │ (index) │  Values   │
// ├─────────┼───────────┤
// │    0    │ 'apples'  │
// │    1    │ 'oranges' │
// │    2    │ 'bananas' │
// └─────────┴───────────┘
console.table( ["apples", "oranges", "bananas"] );
```

#### **console.time()**

Starts a timer with a name specified as an input parameter. Up to 10,000 simultaneous timers can run on a given page.

```javascript
// Outputs:
// default: 0.156ms
console.time();
console.timeEnd();
```

#### **console.timeEnd()**

Stops the specified timer and logs the elapsed time in seconds since it started.

```javascript
// Outputs: 
// default: 0.156ms
console.time();
console.timeEnd();
```

#### **console.timeLog()**

Logs the value of the specified timer to the console.

```javascript
// Outputs
// example: 0.099ms
// example: 0.377ms
console.time("example");
console.timeLog("example");
console.timeEnd("example");
```

#### **console.trace()**

Outputs a stack trace.

```javascript
let example = 5;

// Outputs
// Trace: 5...
console.trace( example );
```

#### **console.warn()**

Outputs a warning message. You may use string substitution and additional arguments with this method.

```javascript
console.warn("Warning!");
```

### JSON Static Methods

#### **JSON.parse(text)**

Parse the string text as JSON and transform the value into an object literal. If an error occurs during the transformation, a `SyntaxError` will be thrown.

```javascript
const jsonString = '{"property1":1,"property2":2}';

// Outputs
// { property1: 1, property2: 2 }
console.log ( JSON.parse(jsonString) );
```

#### **JSON.stringify(value[, replacer[, space]])**

Returns a JSON string equal to the specified **value**, translating all properties into string values. The second, optional argument *replacer* allows for changing default translation behaviors like using `undefined` for `null` values.

```javascript
const objectExample = {
  property1: 1,
  property2: 2
}

// Outputs
// {"property1":1,"property2":2}
console.log ( JSON.stringify(objectExample) );
```

The third, optional argument *space* defines the whitespace between properties. (Using, for example, the tab printing symbol, `\t`, would "tabs between each and "pretty print" the values.)

```javascript
const objectExample = {
  property1: 1,
  property2: 2
}

// Outputs
// {
//    "property1": 1,
//    "property2": 2
// }
console.log ( JSON.stringify(objectExample, null, "\t") );
```

### Static Global Functions

JavaScript also defines global functions that can be used from any scope for processing data.

#### **eval(string)**

Evaluates JavaScript code represented as *string*.

**Note:** Using *eval()* is often a security risk and should very rarely be used. Any code run with **eval()** executes in the global scope.

```javascript
const jsString = 'let example = 5;';

eval(jsString);
```

#### **isFinite(x)**

Returns if *value* is a finite number.

```javascript
// Outputs true
console.log ( isFinite(-1) );
```

#### **isNaN(x)**

Returns if *x* is NaN (not-a-number) or not.

```javascript
// Outputs false
console.log ( isNaN(-1) );
```

**Note:** In most cases, the preferred function is **Number.isNaN()** because of how **isNaN()** will attempt to convert values into numbers for testing.

#### **parseFloat(x)**

Parses *x* (possibly converting it into a string first) and returns a floating point (decimal) number.

```javascript
// Outputs 4.56
console.log ( parseFloat("4.56") );
```

#### **parseInt(x, radix)**

Parses a string, *x*, and returns an integer of the specified radix (the base in mathematical numeral systems).

```javascript
// Outputs 4
console.log ( parseInt("4.56") );
```

#### **setInterval(callback, time)**

Set a function **callback** to be called ever milliseconds in *time*.

```javascript
// Outputs
// Hi, there!
// Hi, there!
// Hi, there!
// Hi, there!
// Hi, there!
// Hi, there!
let intervalCount = 5;

let intervalLabel = setInterval(() => {
  
  console.log("Hi, there!");
  
  intervalCount++;

  if(intervalCount > 10) {
    clearInterval(intervalLabel);
  }

}, 1000);
```

#### **setTimeout(callback, time)**

Set a function **callback** to be called after milliseconds in *time*.

```javascript
// Outputs (after 1 second)
// "Hi, there!"
setTimeout(() => {
  
  console.log("Hi, there!");

}, 1000);
```

### **clearInterval(label)**

Stop (clear) an interval based on its *value*.

```javascript
// Outputs
// Hi, there!
// Hi, there!
// Hi, there!
// Hi, there!
// Hi, there!
// Hi, there!
let intervalCount = 5;

let intervalLabel = setInterval(() => {
  
  console.log("Hi, there!");
  
  intervalCount++;

  if(intervalCount > 10) {
    clearInterval(intervalLabel);
  }

}, 1000);
```
