
### Spread Operator

In JavaScript ES5, either a `for()` loop or some other functionality was needed to use the entire contents of an array. In ES6, an additional operator, `...`, the spread operator, was added to for these cases. Used in front of an array, it "spreads" its contents.

```javascript
// Create an array
let arrayExample = [1,2,3,4,5,6,7,8,9,10];
// Use the spread operator to print
//  the entire contents.
console.log(...arrayExample);
```
