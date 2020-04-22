### `Map()`

Along with other data types like String, Boolean, Array, Number, and Set, JavaScript ES6 adds another: Map.

A Map is similar to a Set, but is organized differently. Each entry is added through a (*key*, *value*) format. Each *key* and *value* added can be any valid data type in JavaScript.

- *size*, the current number of entries in the map.
- *get(key)*, returns the *value* associated with the key.
- *has(key)*, returns if the *key* is in the map or not.
- *add(key, value)*, adds an entry to the map.
- *set(key, value)*, updates the *value* for the *key*.
- *delete(key)*, if *key* is in map, the *(key, value)* is removed and returned as an array. Otherwise, returns `false`.
- *entries()*, converts each entry into an array of form `[key, value]` and returns the array.
- *values()*, returns an `Iterable` object for accessing entries in the map in the order they were inserted.
- *forEach(callback)*, accepts a function to be called for each entry in the map.

```javascript
let setExample = Map();
setExample.add("keyOne", 1);
setExample.add(2, "keyTwo");
```
