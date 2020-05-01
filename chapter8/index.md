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
    - [WeakSet Methods](#weakset-methods)
      - [WeakSet **add(value)**](#weakset-addvalue)
      - [WeakSet **has(value)**](#weakset-hasvalue)
      - [WeakMap **delete(value)**](#weakmap-deletevalue)
  - [**WeakMap()**](#weakmap)
    - [WeakMap Methods](#weakmap-methods)
      - [WeakMap **set(key, value)**](#weakmap-setkey-value)
      - [WeakMap **get(key)**](#weakmap-getkey)
      - [WeakMap **has(key)**](#weakmap-haskey)
      - [WeakMap **delete(key)**](#weakmap-deletekey)

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

As **Set** is a special **Array** object, **WeakSet** is a special version of **Set**. It carries the same constraint that all entries be *unique*, but also specializes in one more rule: only *objects* can be stored.

The use of the word `weak` also implies a *weakly-held* relationship to its contents. If no other references to the objects held within it exist, they will be garbage collected.

**Note:** JavaScript handles all memory management automatically. In programming terminology, "garbage collection" is a service that acts to free up memory in running code through examining variables that are no longer being used and removing them from active memory.

Because all objects are weakly-held, there is also no available *size* of the number of objects held.

### WeakSet Methods

#### WeakSet **add(value)**

Adds the object **value** to the weak set.

```javascript
const objectExample = {
  property1: 1
};

let weakSetExample = new WeakSet();
weakSetExample.add(objectExample);
```

#### WeakSet **has(value)**

Returns if object **value** is in the set or not.

```javascript
const objectExample = {
  property1: 1
};

let weakSetExample = new WeakSet();
weakSetExample.add(objectExample);

// Outputs true
console.log( weakSetExample.has(objectExample) );
```

#### WeakMap **delete(value)**

Removes an object, **value**, from the weak map.

```javascript
const objectExample = {
  property1: 1
};

let weakSetExample = new WeakSet();
weakSetExample.add(objectExample);

weakSetExample.delete(objectExample)

// Outputs false
console.log( weakSetExample.has(objectExample)  );
```

## **WeakMap()**

As **Map** is a special **Array** object, **WeakMap** is a special version of **Map**. It carries the same constraint that all entries be *unique*, but also specializes in one more rule: only *objects* can be stored as keys.

Each **key** must be an object. However, values can be any other arbitrary values available in JavaScript.

The use of the word `weak` also implies a *weakly-held* relationship to its contents. If no other references to the objects held within it exist, they will be garbage collected.

**Note:** JavaScript handles all memory management automatically. In programming terminology, "garbage collection" is a service that acts to free up memory in running code through examining variables that are no longer being used and removing them from active memory.

Because all objects are weakly-held, there is also no available *size* of the number of objects held.

### WeakMap Methods

#### WeakMap **set(key, value)**

Adds object **key** with *value* to the weak map.

```javascript
const objectExample = {
  property1: 1
};

let weakMapExample = new WeakMap();
weakMapExample.set(objectExample, 5);
```

#### WeakMap **get(key)**

Returns *value* matching the **key** provided. If **key** is not in map, it returns `undefined`.

```javascript
const objectExample = {
  property1: 1
};

let weakMapExample = new WeakMap();
weakMapExample.set(objectExample, 5);

// Outputs 5
console.log( weakMapExample.get(objectExample)  );
```

#### WeakMap **has(key)**

Returns if object **key** is within the weak map or not.

```javascript
const objectExample = {
  property1: 1
};

let weakMapExample = new WeakMap();
weakMapExample.set(objectExample, 5);

// Outputs true
console.log( weakMapExample.has(objectExample)  );
```

#### WeakMap **delete(key)**

If **key** is in map, it is removed.

```javascript
const objectExample = {
  property1: 1
};

let weakMapExample = new WeakMap();
weakMapExample.set(objectExample, 5);

weakMapExample.delete(objectExample);

// Outputs false
console.log( weakMapExample.has(objectExample)  );
```
