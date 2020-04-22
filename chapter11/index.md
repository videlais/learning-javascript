### Static Class Properties and Functions

Some JavaScript environments support using the experimental keyword `static`. It can be paired with both functions and public fields in a class.

When used with a function, it changes a function from being part of an instance (object) to being part of the *class* itself. It creates a single copy across *all* instances of the class, making it "static" to the class. It also, because it is static, comes with some extra rules.

A static function:

- Can be called using the name of the class
- Can only call or reference other static functions and values
- Cannot use `this`
- Cannot use *super()*

As the function is static to the class and not any particular instance, it does not have access to `this` or *super()*. However, it can be called using the name of the class outside of any instance of the class.

```javascript
class ExampleClass {
  static staticFunction() {
    return 'Static method has been called';
  }
}

console.log( ExampleClass.staticFunction() );
```

A static public field in a class works the same as a static function: it can be used with the name of the class outside of any instance. It is "static" to the class, after all.

```javascript
class ExampleClass {

  static publicFieldExample = 5;

}

console.log( ExampleClass.publicFieldExample );

```
