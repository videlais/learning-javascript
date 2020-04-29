# Promises

- [Promises](#promises)
  - [Reviewing Callback Functions](#reviewing-callback-functions)
  - [Waiting for a Future](#waiting-for-a-future)
  - [**then()**](#then)
  - [`async` and `await`](#async-and-await)
  - [Working with **window.fetch()**](#working-with-windowfetch)

## Reviewing Callback Functions

In JavaScript, the use of callback functions have a long history. Methods like **forEach()**, as part of array objects, for example, accept a callback function.

```javascript
let arrayExample = [1,2,3];

arrayExample.forEach(
  function(position, index) {
    console.log(`The position is ${position} and its index is ${index}`);
  }
)
```

In these case, the callback function is called on every loop. However, there are also cases where a callback function would call another that would call another. In these cases, the callback functions would create a complicated and hard to debug cycle, a "callback hell!"

This becomes even more complicated when any function within the process takes longer than normal. There is no way to know, at any one step, if there was a problem with a specific code or the overall process.

## Waiting for a Future

To help with situations where a function might take an extended period of time, JavaScript ES6 added a new concept: **Promise**

A promise is a future outcome. A person may promise to love someone forever or that they will not do something. It is something that occurs *in the future*.

In JavaScript, a **Promise** is a special type of functionality that will either resolve or reject in the future. When that happens, either one callback function or another will be called.

Some functionality in JavaScript are built on Promises, but one can be created (like any other object) through using the `new` keyword.

```javascript
let example = new Promise();
```

The **Promise** object accepts a callback function with two arguments: **resolve()** and **reject()**.

The **resolve()** function "resolves" the promise and fulfils it. The **reject()** function rejects the promise.

```javascript
let example = new Promise((resolve, reject) => {
  // To resolve, call resolve().
  // To reject, call reject().
});
```

## **then()**

The result of a promise, resolved or rejected, can be processed through a special function named **then()**. It also accepts two function parameters. If the promise was fulfilled, it calls the first function. If the promise was rejected, it calls the second.

```javascript
// Create a new object based on 'Promise'
let testing = new Promise(
  // Pass a function to 'Promise'
  //
  // The first argument to the function
  //  is resolve() and the second, reject()
  (resolve, reject) => {
    let someValue = 5;
    // Resolve the promise and return a value
    resolve(someValue);
});

// Using then(), determine what happened.
//
// If the promise resolved, the first function
//  will be called. If it was rejected, the
//  second function will be called.
testing.then(
  // First, resolving function
  (value) => {
    console.log(value);
  },
  // Second, rejecting function
  (value) => {
    console.log(value);
  }
);
```

Promises allow for *asynchronous* functions. Because promises are either fulfilled or reject in the future, the callback functions as part of its **then()** can be called at a different time than the code around it. This allows for things like waiting to connect to a server or processing large amounts of data.

Once the promise finishes, it will either resolve or reject, and then the parameters to the **then()** function will be called.

## `async` and `await`

Promises allow for *asynchronous* functions. However, they can also create problems when code is waiting for a promise to either fulfill or reject before continuing. To prevent a problem of more callback functions calling others that call others, ES6 also added two new keywords that work specifically with promises: `async` and `await`.

The `await` keyword, as its name might imply, "waits" for a promise to finish. It also simply takes whatever would have been given to the **then()** functions, whatever is passed to the internal **resolve()** or **reject()** functions, and returns it.

However, to signal that some code should "wait," the keyword `async` must always be used in front of the function in which the `await` keyword is used. This marks the function as *asynchronous* and tells JavaScript that it will finish at some future point and it should not wait for it.

```javascript
async function AsyncExample() {

  let testing = new Promise((resolve, reject) => {
    let someValue = 5;
    resolve(someValue);
  });

  let promiseResult = await testing;

  console.log(promiseResult);

}

AsyncExample();
```

## Working with **window.fetch()**

In browser environments, there is a function call **window.fetch()** that is a light-weight way to retrieve data. (In Node.js, the package [node-fetch](https://www.npmjs.com/package/node-fetch) can also be used in server contexts.)

The function **fetch()** is based on promises. It accepts a first argument of a URL and an optional second argument of different options such as which HTTP request method to use and what headers to use.

The use of the **then()** function (or using `await` and `async`) provides the resolving function with a **[Response](https://developer.mozilla.org/en-US/docs/Web/API/Response)** object.

This object has functions that can process data which, themselves, also work on promises. For example, the **json()** function, which translate text into objects, can be used after the initial **fetch()** promise.

```javascript
async function fetchExample() {
  // Wait for fetch()
  let response = await fetch(URL);

  // Wait for processing to finish
  let processedObject = await response.json();

  console.log(processedObject);

}

fetchExample();
```
