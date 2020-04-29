# `Set()`, `Map()`, `WeakSet()`, and `WeakMap()`

- [`Set()`, `Map()`, `WeakSet()`, and `WeakMap()`](#set-map-weakset-and-weakmap)
  - [`Set()`](#set)
    - [Set Properties](#set-properties)
      - [Set *size*](#set-size)
    - [Set Methods](#set-methods)
      - [Set *has(value)*](#set-hasvalue)
      - [Set *add(value)*](#set-addvalue)
      - [Set *delete(value)*](#set-deletevalue)
      - [Set *clear()*](#set-clear)
      - [Set *entries()*](#set-entries)
      - [Set *values()*](#set-values)
      - [Set *forEach(callback)*](#set-foreachcallback)
  - [`Map()`](#map)
    - [Map Properties](#map-properties)
      - [Map *size*](#map-size)
    - [Map Methods](#map-methods)
      - [Map *get(key)*](#map-getkey)
      - [Map *has(key)*](#map-haskey)
      - [*add(key, value)*](#addkey-value)
      - [*set(key, value)*](#setkey-value)
      - [*delete(key)*](#deletekey)
      - [*entries()*](#entries)
      - [*values()*](#values)
      - [*forEach(callback)*](#foreachcallback)
  - [`WeakSet()`](#weakset)
    - [WeakSet Properties](#weakset-properties)
    - [WeakSet Methods](#weakset-methods)
  - [`WeakMap()`](#weakmap)
    - [WeakMap Properties](#weakmap-properties)
    - [WeakMap Methods](#weakmap-methods)

## `Set()`

Along with other object data types like Function and Array, JavaScript ES6 adds another: Set.

A Set is similar to an Array, but has one specific rule: each value *must* be unique.

Sets are created through the global constructor `Set()`. Unlike Arrays, values cannot be passed into a Set using square brackets. They must be added through the function *add()*.

```javascript
let setExample = Set();
setExample.add(1);
setExample.add("Hello!");
```

`Set` also provides the following properties and methods:

### Set Properties

#### Set *size*

Contains the current number of entries in the set.

### Set Methods

#### Set *has(value)*

Returns if the *value* is in the set or not.

#### Set *add(value)*

Adds a value to the set.

#### Set *delete(value)*

If *value* is in set, it is removed and returned. Otherwise, returns `false`.

#### Set *clear()*

Delete all entries in the set.

#### Set *entries()*

Converts each entry into an array of form `[key, value]` where both are the same value of the entry.

#### Set *values()*

Returns an `Iterable` object for accessing entries in the set in the order they were inserted.

#### Set *forEach(callback)*

Accepts a function to be called for each entry in the set.

## `Map()`

A Map is similar to a Set, but is organized differently. Each entry is added through a (*key*, *value*) format. Each *key* and *value* added can be any valid data type in JavaScript.

### Map Properties

#### Map *size*

Contains the current number of entries in the map.

### Map Methods

#### Map *get(key)*

Returns the *value* associated with the key.

#### Map *has(key)*

Returns if the *key* is in the map or not.

#### *add(key, value)*

Adds an entry to the map.

```javascript
let setExample = Map();
setExample.add("keyOne", 1);
setExample.add(2, "keyTwo");
```

#### *set(key, value)*

Updates the *value* for the *key*.

#### *delete(key)*

If *key* is in map, the *(key, value)* is removed and returned as an array. Otherwise, returns `false`.

#### *entries()*

Converts each entry into an array of form `[key, value]` and returns the array.

#### *values()*

Returns an `Iterable` object for accessing entries in the map in the order they were inserted.

#### *forEach(callback)*

Accepts a function to be called for each entry in the map.

## `WeakSet()`

### WeakSet Properties

### WeakSet Methods

## `WeakMap()`

### WeakMap Properties

### WeakMap Methods
