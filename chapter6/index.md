
### `async` and `await`

Promises allow for *asynchronous* functions. However, they can also create problems when code is waiting for a promise to either fulfill or reject before continuing. To prevent a problem of more callback functions calling others that call others, ES6 also added two new keywords that work specifically with promises: `async` and `await`.

The `await` keyword, as its name might imply, "waits" for a promise to finish. It also simply takes whatever would have been given to the *then()* functions, whatever is passed to the internal *resolve()* or *reject()* functions, and returns it.

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
