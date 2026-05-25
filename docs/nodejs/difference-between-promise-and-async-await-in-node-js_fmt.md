# Promise与Async/Await在Node.js中的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-promise-and-async-await-in-node-js/](https://www.geeksforgeeks.org/difference-between-promise-and-async-await-in-node-js/)

在NodeJS或JavaScript中有不同的处理操作的方法。对于异步执行，不同的进程同时运行，并在每个进程的结果可用时进行处理。在NodeJS或JavaScript中有不同的方法来处理异步代码，它们是：

*   [回调](https://www.geeksforgeeks.org/node-js-callback-concept/)
*   [Promise](https://www.geeksforgeeks.org/promises-in-node-js/)
*   [Async/Await](https://www.geeksforgeeks.org/using-async-await-in-node-js/)

## 1. Promise

Node中的Promise类似于现实生活中的承诺。这是一定会有所作为的保证。`Promise`用于跟踪异步事件是否已经执行，并确定事件发生后会发生什么。它是一个具有3种状态的对象，即：

*   `pending`：初始状态，事件发生前。
*   `fulfilled`：操作成功完成后。
*   `rejected`：如果操作在执行过程中出现错误，则Promise失败。

**示例：** 向数据库服务器请求数据时，`Promise`处于`pending`状态，直到收到数据。如果数据接收成功，则Promise处于`fulfilled`状态，如果数据无法成功接收，则Promise处于`rejected`状态。

**Promise的错误处理：** 对于成功解决的Promise，我们使用`.then()`方法，而对于被拒绝的Promise，我们使用`.catch()`方法。使用`.then()`或`.catch()`方法处理Promise后，我们可以使用`.finally()`方法。`.finally()`方法里面的代码会运行一次，而不管Promise的状态如何。

**示例：**

```js
<script>
  const promise = new Promise(function (resolve, reject) {
    const string1 = "geeksforgeeks";
    const string2 = "geeksforgeeks";
    if (string1 === string2) {
      resolve();
    } else {
      reject();
    }
  });

promise
    .then(function () {
      console.log("Promise resolved successfully");
    })
    .catch(function () {
      console.log("Promise is rejected");
    });
</script>
```

**输出：**

```js
Promise resolved successfully
```

## 2. Async/Await

`async/await`用于处理异步函数中的Promise。它基本上是Promise的语法糖。它只是重新设计代码的包装器，并使Promise更容易阅读和使用。它使异步代码看起来更像同步/过程代码，更容易理解。

`await`只能在`async`函数中使用。它用于调用异步函数，并等待它`resolve`或`reject`。`await`会阻塞其所在的`async`函数中的代码执行。

**Async/Await中的错误处理：** 对于成功解决的Promise，我们使用`try`，对于被拒绝的Promise，我们使用`catch`。要在使用`try`或`catch`处理完Promise后运行代码，我们可以使用`.finally()`方法。`.finally()`方法里面的代码会运行一次，而不管Promise的状态如何。

**示例：**

```js
<script>
  const helperPromise = function () {
    const promise = new Promise(function (resolve, reject) {
      const x = "geeksforgeeks";
      const y = "geeksforgeeks";
      if (x === y) {
        resolve("Strings are same");
      } else {
        reject("Strings are not same");
      }
    });

    return promise;
  };

  async function demoPromise() {
    try {
      let message = await helperPromise();
      console.log(message);
    } catch (error) {
      console.log("Error: " + error);
    }
  }

  demoPromise();
</script>
```

**输出：**

```js
Strings are same
```

## Promise与Async/Await的区别

| **序号** | **Promise** | **Async/Await** |
| :--- | :--- | :--- |
| **1.** | `Promise`是一个对象，代表一个操作的中间状态，并保证在未来某个时间完成。 | `async/await`是Promise的语法糖，是一个使代码执行更同步的包装器。 |
| **2.** | Promise有三种状态：`fulfilled`、`rejected`和`pending`。 | 它没有状态。它返回一个Promise，要么解决，要么拒绝。 |
| **3.** | 如果函数`fxn1`要在Promise之后执行，`promise.then(fxn1)`会将`fxn1`调用添加到回调链中，然后继续执行当前函数。 | 如果函数`fxn1`要在`await`之后执行，那么`await X()`会暂停当前函数的执行，然后执行`fxn1`。 |
| **4.** | 错误处理使用`.then()`和`.catch()`方法。 | 错误处理使用`try`和`catch`方法。 |
| **5.** | Promise链有时会变得难以理解。 | 与Promise链相比，使用`async/await`更容易阅读和理解程序流程。 |