# Reviewing Variables

- [Reviewing Variables](#reviewing-variables)
  - [Introduction to Variables](#introduction-to-variables)
  - [Assigning Values](#assigning-values)
  - [Examining `let`](#examining-let)
  - [Adding `const`](#adding-const)
  - [Types of Data](#types-of-data)
    - [Data Primitives](#data-primitives)
      - [Boolean](#boolean)
      - [`null`](#null)
      - [`undefined`](#undefined)
      - [Number](#number)
      - [String](#string)
    - [Data Collections](#data-collections)
      - [`Object`](#object)
      - [`Array`](#array)
  - [Mathematics with Variables](#mathematics-with-variables)
    - [Order of Operations](#order-of-operations)
  - [Working with Strings](#working-with-strings)
  - [Working with Arrays](#working-with-arrays)
  - [Object Literals](#object-literals)

## Introduction to Variables

We can think of coding like making a cake. Sometimes we want extra frosting -- yum! -- and sometimes we something more practical. The amounts we change in making the cake are *variable*. They change depending on what we want the outcome to be.

In programming, we use special keywords to mark something as a variable. We write "this value might change" and use a special keyword to show that's what we mean. In JavaScript, that special keyword is `let`. It marks what value a variable starts with in the code.

Variable *names* also have a special rule. They can contain letters, numbers, and the underscore, but no other special characters -- not even spaces! Because of this rule, variables are often written in what is called camel case, often written as camelCase. Without spacing between words, the first letter of the second word, and all other words, are capitalized to help better explain its usage.

**Let's look at an example:**

```javascript
let anExampleValue = 5;
```

In the above code, the keyword `let` is used. It marks what follows, the *variable name*, as containing some sort of value. The value given to it is what is on the other side of the equal sign.

We explain this as "give this variable the following value" where the variable, and the keyword explaining it, are on one side of the equal sign and the value is on the other.

The above code is an example of *assignment*. We are *assigning* a value to the variable. We say "for this variable, assign it the following value."

We are also *defining* the variable. Its *definition* is its initial value. We are telling the code to create this variable, using the keyword `let`, and to set its initial value.

*What if we want to change its value later?*

## Assigning Values

One of the most common operations in programming is *assignment*. Using a single equal sign, a value is *assigned* to a variable. This can happen when variables are *defined*, but it can also occur when a new value is *assigned* to an existing variable. Such an action is still an *assignment*. A new value is being assigned!

```javascript
let example = 5;
example = 6;
```

In the above code, a variable is defined, *example*, and assigned a new value. On the next line of code, it is assigned a new value! Both are examples of *assignment*, but the first is also a *definition*. It defines a variable whose value is changed.

*What's with the semicolons?*

Many programming languages, JavaScript among them, use the semicolon, `;`, to mark the end of a line of code. Programs are made up of potentially many lines of code. Each one, unless under special circumstances, end with a semicolon.

Semicolons help tell the computer. "Do this thing and then move to the next line." As coding, like with writing itself, is added one line at a time, this helps both developers and the computer know when one thought ends and the next begins. They can be thought of periods, `.`, marking the end of something before moving on to the next thing.

## Examining `let`

The keyword `let` is used when defining a variable, but it also implies something to the code. This is a variable that will probably change values. The keyword `let` signals that the value *can* change. We "let" it potentially change in the future.

```javascript
let example = 5;
example = 6;
```

Returning to the earlier example, the keyword `let` was used to initial define a variable. It was then *assigned* a new value. We "let" it change!

*What about if we don't want variable to change?*

## Adding `const`

The keyword `const` is used for values that will not change after being defined. These values are *constant*. Any attempt to change their values will result in an error!

```javascript
const example = 5;
// The following code will result in an error!
example = 6;
```

The keyword `const` helps protect variables. When they are *defined* using the keyword, they become constant values. They cannot while the code is run, and any attempts will produce an error.

## Types of Data

Variables are defined using the keywords `let` and `const` during operations called *assignment*. They are *assigned* values.

*What kinds of values can variables be?*

Computers are not very smart. They must be told exactly how much room each type value is so they can store it. In JavaScript, this done through using different *types* of data.

A *data type* is a way to mark values of a certain *type*. This helps the computer know how much space to use to store the value and enables certain functionality. Depending on the *type*, it can be used in different ways.

### Data Primitives

Programmers often use the term *primitive* in regard to data types to explain that the values cannot be broken down into smaller units. Much like money can often be broken down from its paper form into coins, the coins themselves are the *primitive* form. There are no smaller forms.

JavaScript supports multiple *primitive data types*:

#### Boolean

Named after George Boole, who invented a form of algebra to represent their values in the mid-19th century, this type of data can either be `true` or `false`. They represent the ability of the computer to store 1 or 0.

Boolean values can *only* be the values of the exact words, all lowercase, of `true` and `false`;

```javascript
let booleanExample = true;
let secondBooleanExample = false;
```

#### `null`

Sometimes, there is a need to represent a value that is outside all others. This where the keyword, and value, `null` is used. It is used to mark that a variable has a value, but that the value is a placeholder.

```javascript
let nullExample = null;
```

#### `undefined`

If `null` is a non-value value, the keyword `undefined` is the reverse. If a variable does not have a value, its value is `undefined`. This means that any variables not assigned a value will have one: `undefined`.

```javascript
let undefinedExample;
```

#### Number

Any number of any form, be it a whole number, 5, or a decimal, 3.14, is a Number in JavaScript. It is a *primitive* that represents all numbers.

```javascript
let numberExample = 5;
```

#### String

Programming is written using words. This makes storing words and phrases potentially difficult. To mark the storage of words, quotation marks are used. Either single quotation marks, `'`, or double-quotation marks, `"`, can be used around a collection of letters, numbers, spaces, or other special characters. This marks them as a *String*.

```javascript
let stringExample = "Hello, world!";
```

### Data Collections

Beyond *primitives*, JavaScript also supports other *types* of data that are collections. This starts with *Object*, which define the shape of the others like *Array*. (Some collections are covered in later chapter.)

#### `Object`

In JavaScript, an *object* is a collection of *properties*. These can be any of the *other* data types, including itself!

Objects "collect" the other data types inside itself. All properties are "wrapped" through curly brackets, which define the values within as part of itself.

#### `Array`

An *Array* is a special type of object where order is important. Its values are defined using square brackets with commas between them.

```javascript
let arrayExample = [1, 3, "Hello!"];
```

## Mathematics with Variables

Mathematics can be preformed with Number values. For example, `5 + 5` will become the value 10.

```javascript
let numberExample = 5;
numberExample = 5 + 5;
```

As variables "stand in" for their values, they can also be used as part of mathematical expressions.

```javascript
let numberExample = 5;
numberExample = numberExample + 5;
```

Any use of the variable will be translated into its value.

### Order of Operations

Mathematical operations are carried out in a specific order in JavaScript.

The list is quite expansive, but some of the specific order includes the following:

- Groupings
- New Objects
- Properties
- Multiplication
- Division
- Addition
- Subtraction

## Working with Strings

While Numbers can be added together, String values have a different special operation associated with them: *concatenation*.

This operation, *concatenation*, literally means "to put together."

With the addition symbol is used with String values, they are combined!

```javascript
let stringExample = "Hello";
stringExample = stringExample + ", world!";
```

## Working with Arrays

## Object Literals
