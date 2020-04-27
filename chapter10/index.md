
### `Set()`

Along with other data types like String, Boolean, Array, and Number, JavaScript ES6 adds another: Set.

A Set is similar to an Array, but has one specific rule: each value *must* be unique.

Sets are created through the constructor `Set()`. Unlike Arrays, values cannot be passed into a Set. They must be added through the function *add()*.

```javascript
let setExample = Set();
setExample.add(1);
setExample.add("Hello!");
```

`Set` also provides the following properties and functions:

- *size*, the current number of entries in the set.
- *has(value)*, returns if the value is in the set or not.
- *add(value)*, adds a value to the set.
- *delete(value)*, if value is in set, it is removed and returned. Otherwise, returns `false`.
- *clear()*, delete all entries in the set.
- *entries()*, converts each entry into an array of form `[key, value]` where both are the same value of the entry.
- *values()*, returns an `Iterable` object for accessing entries in the set in the order they were inserted.
- *forEach(callback)*, accepts a function to be called for each entry in the set

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
