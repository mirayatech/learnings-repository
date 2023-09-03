# 🎱 Non-blocking I/O in Node.js

Node.js is famous for its efficient and scalable non-blocking I/O model. In simple terms, this means that I/O operations happen asynchronously, allowing your program to do multiple things at once. Here's how it works:

🔄 **Event Loop**: Node.js relies on an event loop to manage I/O. When you initiate an I/O operation, Node.js registers a callback with the event loop. Once the operation completes, the callback is triggered, allowing you to handle the result.

🎣 **Callbacks**: Callbacks are functions that handle the results of asynchronous operations. Node.js uses callbacks extensively to let your program continue with other tasks while waiting for I/O operations to finish.

🌥️ **Non-Blocking APIs**: Node.js offers non-blocking APIs (like those in the `fs` module) for performing I/O operations. These APIs return control to your program immediately, so you can keep executing code. When the I/O operation completes, the specified callback function is invoked with the result.

🧶 **Single-Threaded**: Node.js is single-threaded, meaning it uses a single thread to handle I/O operations. This efficient approach allows Node.js to handle many connections without consuming excessive resources.

## 🪧 Example

**Blocking code example**

```javascript
const getUserSync = (userId) => {
  const users = {
    1: { name: "John", age: 35 },
    2: { name: "Jane", age: 28 },
  };
  return users[userId];
};

const user = getUserSync(1);
console.log(user);
```

In this code, `getUserSync` is blocking because it waits for the result before continuing.

**Non-blocking code example**

```javascript
const getUserAsync = (userId, callback) => {
  const users = {
    1: { name: "John", age: 35 },
    2: { name: "Jane", age: 28 },
  };
  setTimeout(() => {
    callback(users[userId]);
  }, 1000);
};

getUserAsync(1, (user) => {
  console.log(user);
});
```

Here, `getUserAsync` is non-blocking because it doesn't wait for the result, and the callback is invoked once the data is ready.

## 💡 Remember

- **Synchronous Node.js code** is like waiting in line; it makes the program wait for each task to finish before moving to the next one.

- **Asynchronous Node.js code** is like multitasking; it lets the program keep doing other things while waiting for certain tasks to finish, using callbacks, Promises, or async/await to manage them when they're done.
