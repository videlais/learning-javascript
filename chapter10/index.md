# **Set()**, **Map()**, **WeakSet()**, and **WeakMap()**

- [**Set()**, **Map()**, **WeakSet()**, and **WeakMap()**](#set-map-weakset-and-weakmap)
  - [**Set()**](#set)
    - [Set Properties](#set-properties)
      - [Set *size*](#set-size)
    - [Set Methods](#set-methods)
      - [Set **has(value)**](#set-hasvalue)
      - [Set **add(value)**](#set-addvalue)
      - [Set **delete(value)**](#set-deletevalue)
      - [Set **clear()**](#set-clear)
      - [Set **entries()**](#set-entries)
      - [Set **values()**](#set-values)
      - [Set **forEach(callback)**](#set-foreachcallback)
  - [**Map()**](#map)
    - [Map Properties](#map-properties)
      - [Map *size*](#map-size)
    - [Map Methods](#map-methods)
      - [Map **get(key)**](#map-getkey)
      - [Map **has(key)**](#map-haskey)
      - [Map **set(key, value)**](#map-setkey-value)
      - [Map **delete(key)**](#map-deletekey)
      - [Map **entries()**](#map-entries)
      - [Map **values()**](#map-values)
      - [Map **forEach(callback)**](#map-foreachcallback)
  - [**WeakSet()**](#weakset)
    - [WeakSet Properties](#weakset-properties)
    - [WeakSet Methods](#weakset-methods)
  - [**WeakMap()**](#weakmap)
    - [WeakMap Properties](#weakmap-properties)
    - [WeakMap Methods](#weakmap-methods)

## **Set()**

A **Set** is a special type of **Array** object with one specific rule: each value *must* be unique.

Sets are created through the global constructor **Set()**. Unlike Arrays, values cannot be passed into a Set using square brackets. They must be added through the function **add()**.

`Set` also provides the following properties and methods:

### Set Properties

#### Set *size*

Contains the current number of entries in the set.

```javascript
let setExample = new Set();
setExample.add("1");

// Outputs 1
console.log( setExample.size );
```

### Set Methods

#### Set **has(value)**

Returns if the *value* is in the set or not.

```javascript
let setExample = new Set();
setExample.add("1");

// Outputs true
console.log ( setExample.has("1") );
```

#### Set **add(value)**

Adds a value to the set.

```javascript
let setExample = new Set();
setExample.add(1);
setExample.add("Hello!");
```

#### Set **delete(value)**

If *value* is in set, it is removed and returned. Otherwise, returns `false`.

```javascript
let setExample = new Set();
setExample.add(1);

// Outputs 1
console.log ( setExample.size );

setExample.delete(1);

// Outputs 0
console.log ( setExample.size );
```

#### Set **clear()**

Delete all entries in the set.

```javascript
let setExample = new Set();
setExample.add(1);

// Outputs 1
console.log ( setExample.size );

setExample.clear();

// Outputs 0
console.log ( setExample.size );
```

#### Set **entries()**

Converts each entry into an array of form `[key, value]` where both are the same value of the entry.

```javascript
let setExample = new Set();
setExample.add(1);
setExample.add("hello!");

// Outputs { [ 1, 1 ], [ 'hello!', 'hello!' ] }
console.log ( setExample.entries() );
```

#### Set **values()**

Returns an `Iterable` object for accessing entries in the set in the order they were inserted.

```javascript
let setExample = new Set();
setExample.add(1);
setExample.add("hello!");

// Outputs [Set Iterator] { 1, 'hello!' }
console.log ( setExample.values() );
```

#### Set **forEach(callback)**

Accepts a function to be called for each entry in the set.

```javascript
let setExample = new Set();
setExample.add(1);
setExample.add("hello!");

// Outputs
// 1
// hello!
setExample.forEach((entry) => {
  console.log( entry );
});
```

## **Map()**

A **Map** a special type of **Array**, but is organized differently. Each entry is added through a (*key*, *value*) format. Each *key* and *value* added can be any valid data type in JavaScript.

**Note:** Like **Set()**, entries are added through its own **add()** method.

### Map Properties

#### Map *size*

Contains the current number of entries in the map.

```javascript
let mapExample = new Map();
mapExample.set("key1", "1");
mapExample.set("key2", "2");

// Outputs 2
console.log( mapExample.size );
```

### Map Methods

#### Map **get(key)**

Returns the *value* associated with the key.

```javascript
let mapExample = new Map();
mapExample.set("key1", "1");

// Outputs "1"
console.log( mapExample.get("key1") );
```

#### Map **has(key)**

Returns if the *key* is in the map or not.

```javascript
let mapExample = new Map();
mapExample.set("key1", "1");

// Outputs true
console.log( mapExample.has("key1") );
```

#### Map **set(key, value)**

Updates the *value* for the *key*.

```javascript
let mapExample = new Map();
mapExample.set("key1", "1");
mapExample.set("key2", "2");

// Outputs 2
console.log( mapExample.size );
```

#### Map **delete(key)**

If *key* is in map, the *(key, value)* is removed and returned as an array. Otherwise, returns `false`.

```javascript
let mapExample = new Map();
mapExample.set("key1", "1");

mapExample.delete("key1");

// Outputs 0
console.log( mapExample.size );
```

#### Map **entries()**

Converts each entry into an array of form `[key, value]` and returns the array.

```javascript
let mapExample = new Map();
mapExample.set("key1", "1");

// Outputs
// [Map Entries] { [ 'key1', '1' ] }
console.log( mapExample.entries() );
```

#### Map **values()**

Returns an `Iterable` object for accessing entries in the map in the order they were inserted.

```javascript
let mapExample = new Map();
mapExample.set("key1", "1");

// Outputs
// [Map Iterator] { '1' }
console.log( mapExample.values() );
```

#### Map **forEach(callback)**

Accepts a function to be called for each entry in the map.

```javascript
let mapExample = new Map();
mapExample.set("key1", "1");

// Outputs 1 key
mapExample.forEach((value, key) => {
  console.log(value, key);
});
```

## **WeakSet()**

### WeakSet Properties

### WeakSet Methods

## **WeakMap()**

### WeakMap Properties

### WeakMap Methods
