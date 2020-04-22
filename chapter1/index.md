# Variables

- [Variables](#variables)
  - [Introduction to Variables](#introduction-to-variables)
  - [Assigning Values](#assigning-values)
  - [Examining `let`](#examining-let)
  - [Adding `const`](#adding-const)
  - [Types of Data](#types-of-data)
  - [Mathematics with Variables](#mathematics-with-variables)
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

The keyword `const` helps protect variables. When they are *defined* using the keyword, they become constant values. They cannot change during the code and any attempts will produce an error.

## Types of Data

## Mathematics with Variables

## Working with Strings

## Working with Arrays

## Object Literals
