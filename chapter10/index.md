
### Public Instance Fields

In JavaScript ES6, it is possible to create a *public instance field*. What this means is that a field (a property or function) is created outside of the *constructor()* function within a class. It is *public* because it acts like a property of the class and is a *field* because it is defined outside of using the `this` keyword.

While still an experimental feature in some JavaScript contexts, it can be used inside of React because Babel understands and can transpile the code for other programs like browsers to understand.

```javascript
class Element {
  instanceExample = 5;
}
```

In the above code, the vale of the public instance field *instanceExample* is 5. This is a property that is added *outside* of the normal usage of the *constructor()*, but is part of any instance of the class.

Instance field can hold any value, which means they can also hold the value of a function.

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

In the above code, the property *newExampleName* is computer inside of the square brackets used as part of the instance field. It is computer and then added to the instance and can be used.

### Private Instance Fields

Normally, all properties of a class are public in JavaScript. Their values can be accessed through their names. With private instance fields, this level of access can be changed. Values can be set to *private* so that only the class, and not even its children, can access it.

To create private instance fields, the hash symbol, `#`, can be used. It can only be used with fields and cannot be defined inside of a *constructor()* function.

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
