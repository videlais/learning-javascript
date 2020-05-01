# ArrayBuffer and Typed Arrays

- [ArrayBuffer and Typed Arrays](#arraybuffer-and-typed-arrays)
  - [Specialized Arrays](#specialized-arrays)
  - [ArrayBuffer](#arraybuffer)
  - [**DataView**](#dataview)
    - [**new DataView(buffer [, byteOffset [, byteLength]])**](#new-dataviewbuffer--byteoffset--bytelength)
    - [DataView Properties](#dataview-properties)
      - [DataView *buffer*](#dataview-buffer)
      - [DataView *byteOffset*](#dataview-byteoffset)
      - [DataView *byteLength*](#dataview-bytelength)
    - [DataView Methods](#dataview-methods)
      - [DataView **getInt8()**](#dataview-getint8)
      - [DataView **getUint8()**](#dataview-getuint8)
      - [DataView **getInt16()**](#dataview-getint16)
      - [DataView **getUint16()**](#dataview-getuint16)
      - [DataView **getInt32()**](#dataview-getint32)
      - [DataView **getUint32()**](#dataview-getuint32)
      - [DataView **getFloat32()**](#dataview-getfloat32)
      - [DataView **getFloat64()**](#dataview-getfloat64)
    - [DataView **getBigInt64()**](#dataview-getbigint64)
      - [DataView **getBigUint64()**](#dataview-getbiguint64)
      - [DataView **setInt8()**](#dataview-setint8)
      - [DataView **setUint8()**](#dataview-setuint8)
      - [**setInt16()**](#setint16)
      - [DataView **setUint16()**](#dataview-setuint16)
      - [DataView **setInt32()**](#dataview-setint32)
      - [DataView **setUint32()**](#dataview-setuint32)
      - [DataView **setFloat32()**](#dataview-setfloat32)
      - [DataView **setFloat64()**](#dataview-setfloat64)
      - [DataView **setBigInt64()**](#dataview-setbigint64)
      - [DataView **setBigUint64()**](#dataview-setbiguint64)
  - [Typed Arrays](#typed-arrays)
    - [TypedArray Properties](#typedarray-properties)
      - [TypedArray *BYTES_PER_ELEMENT*](#typedarray-bytesperelement)
      - [TypedArray *name*](#typedarray-name)
      - [TypedArray *buffer*](#typedarray-buffer)
      - [TypedArray *byteOffset*](#typedarray-byteoffset)
      - [TypedArray *byteLength*](#typedarray-bytelength)
    - [TypedArray Methods](#typedarray-methods)
      - [TypedArray **from()**](#typedarray-from)
      - [TypedArray **of()**](#typedarray-of)
    - [**Int8Array**](#int8array)
    - [**Uint8Array**](#uint8array)
    - [**Uint8ClampedArray**](#uint8clampedarray)
    - [**Int16Array**](#int16array)
    - [**Uint16Array**](#uint16array)
    - [**Int32Array**](#int32array)
    - [**Uint32Array**](#uint32array)
    - [**Float32Array**](#float32array)
    - [**Float64Array**](#float64array)
    - [**BigInt64Array**](#bigint64array)
    - [**BigUint64Array**](#biguint64array)

## Specialized Arrays

In JavaScript, the object **Array** holds a sequence of values often created and accessed through the square bracket notation. However, it is not optimized for more complex tasks like holding binary data or working with specified types of data.

To help with these specialized tasks, JavaScript ES6 includes additional **Array** objects for certain tasks or contexts.

## ArrayBuffer

An **ArrayBuffer** represent a generic, fixed-length sequence of binary data. It is a *buffer* in that its contents cannot be manipulated directly. Instead either a **DataView** or *typed array* must be used.

## **DataView**

A **DataView** is an object for working with **ArrayBuffer** objects. It allows for working with binary data directly through specifying a specific length of the buffer and then using specified methods to access or change data values.

```javascript
var buffer = new ArrayBuffer(2);
let dataViewExample = new DataView(buffer);
```

### **new DataView(buffer [, byteOffset [, byteLength]])**

Its constructor accepts either the entire **buffer** or the **buffer** and optional *byteOffset* and *byteLength* of a subsection of the buffer.

### DataView Properties

#### DataView *buffer*

The **buffer** of the **DataView**. *Read Only*

#### DataView *byteOffset*

The *byteOffset* of **buffer**. If not explicitly set, this is the 0 byte of the buffer. *Read Only*

#### DataView *byteLength*

The *byteLength* of **buffer**. If not explicitly set, this is the length the **buffer**. *Read Only*

### DataView Methods

#### DataView **getInt8()**

Gets a signed 8-bit integer (byte) at the specified byte offset from the start of the view.

#### DataView **getUint8()**

Gets an unsigned 8-bit integer (unsigned byte) at the specified byte offset from the start of the view.

#### DataView **getInt16()**

Gets a signed 16-bit integer (short) at the specified byte offset from the start of the view.

#### DataView **getUint16()**

Gets an unsigned 16-bit integer (unsigned short) at the specified byte offset from the start of the view.

#### DataView **getInt32()**

Gets a signed 32-bit integer (long) at the specified byte offset from the start of the view.

#### DataView **getUint32()**

Gets an unsigned 32-bit integer (unsigned long) at the specified byte offset from the start of the view.

#### DataView **getFloat32()**

Gets a signed 32-bit float (float) at the specified byte offset from the start of the view.

#### DataView **getFloat64()**

Gets a signed 64-bit float (double) at the specified byte offset from the start of the view.

### DataView **getBigInt64()**

Gets a signed 64-bit integer (long long) at the specified byte offset from the start of the view.

#### DataView **getBigUint64()**

Gets an unsigned 64-bit integer (unsigned long long) at the specified byte offset from the start of the view.

#### DataView **setInt8()**

Stores a signed 8-bit integer (byte) value at the specified byte offset from the start of the view.

#### DataView **setUint8()**

Stores an unsigned 8-bit integer (unsigned byte) value at the specified byte offset from the start of the view.

#### **setInt16()**

Stores a signed 16-bit integer (short) value at the specified byte offset from the start of the view.

#### DataView **setUint16()**

Stores an unsigned 16-bit integer (unsigned short) value at the specified byte offset from the start of the view.

#### DataView **setInt32()**

Stores a signed 32-bit integer (long) value at the specified byte offset from the start of the view.

#### DataView **setUint32()**

Stores an unsigned 32-bit integer (unsigned long) value at the specified byte offset from the start of the view.

#### DataView **setFloat32()**

Stores a signed 32-bit float (float) value at the specified byte offset from the start of the view.

#### DataView **setFloat64()**

Stores a signed 64-bit float (double) value at the specified byte offset from the start of the view.

#### DataView **setBigInt64()**

Stores a signed 64-bit integer (long long) value at the specified byte offset from the start of the view.

#### DataView **setBigUint64()**

Stores an unsigned 64-bit integer (unsigned long long) value at the specified byte offset from the start of the view.

## Typed Arrays

A **TypedArray** is an **Array** designed for a specific *type* of data based on how the data is stored in memory. It is created based on working with **ArrayBuffer** as a subset of the data within a larger buffer.

**TypedArray** is not used directly. However, it serves as the prototype object of the other *typed* arrays that use its same properties and methods internally.

### TypedArray Properties

#### TypedArray *BYTES_PER_ELEMENT*

Returns a number value of the element size for the different TypedArray objects.

#### TypedArray *name*

Returns the string value of the constructor name.

#### TypedArray *buffer*

Returns **ArrayBuffer** referenced by the typed array. *Read Only*

#### TypedArray *byteOffset*

The *byteOffset* of **ArrayBuffer** referenced by the typed array. If not explicitly set, this is the 0 byte of the buffer. *Read Only*

#### TypedArray *byteLength*

The *byteLength* of **ArrayBuffer** referenced by the typed array. If not explicitly set, this is the length the **buffer**. *Read Only*

### TypedArray Methods

Based on **Array**, **TypedArray** inherits along the prototype chain all existing **Array** methods.

#### TypedArray **from()**

Creates a new **TypedArray** from an array-like or iterable object.

#### TypedArray **of()**

Creates a new **TypedArray** with a variable number of arguments.

### **Int8Array**

Inherits from **TypedArray**.

Works with values in the range -128 to 127 of 8-bit two's complement signed integer byte data.

### **Uint8Array**

Inherits from **TypedArray**.

Works with values in the range 0 to 255 of 8-bit unsigned integer octet data.

### **Uint8ClampedArray**

Inherits from **TypedArray**.

Works with values in the range 0 to 255 of 8-bit unsigned integer (clamped) octet data.

### **Int16Array**

Inherits from **TypedArray**.

Works with values in the range -32768 to 32767 16-bit two's complement signed integer short data.

### **Uint16Array**

Inherits from **TypedArray**.

Works with values in the range 0 to 65535 of  16-bit unsigned integer unsigned short data.

### **Int32Array**

Inherits from **TypedArray**.

Works with values in the range -2147483648 to 214748364 of 32-bit two's complement signed integer long data.

### **Uint32Array**

Inherits from **TypedArray**.

Works with values in the range 0 to 4294967295 32-bit unsigned integer unsigned long data.

### **Float32Array**

Inherits from **TypedArray**.

Works with values in the range 1.2×10-38 to 3.4×1038 of 32-bit IEEE floating point number (7 significant digits e.g., 1.123456) unrestricted float data.

### **Float64Array**

Inherits from **TypedArray**.

Works with values in the range 5.0×10-324 to 1.8×10308 of 64-bit IEEE floating point number (16 significant digits e.g., 1.123...15) unrestricted double data.

### **BigInt64Array**

Inherits from **TypedArray**.

Works with values in the range -2^63 to 2^63-1 64-bit two's complement signed integer bigint data.

### **BigUint64Array**

Inherits from **TypedArray**.

Works with values in the range 0 to 2^64-1 64-bit unsigned integer bigint data.
