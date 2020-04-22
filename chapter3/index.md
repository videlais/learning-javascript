
### Template Literals

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
