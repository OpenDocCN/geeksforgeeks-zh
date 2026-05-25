# JavaScript Promise

> 原文: [https://www.geeksforgeeks.org/javascript-promises/](https://www.geeksforgeeks.org/javascript-promises/)

**Promise** 用于处理 JavaScript 中的异步操作。当处理多个异步操作时，它们很容易管理，其中回调会创建回调地狱，导致无法管理的代码。

在 Promise 之前，使用了事件和回调函数，但是它们的功能有限，并且产生了难以管理的代码。多个回调函数会创建回调地狱，导致无法管理的代码。此外，任何用户都不容易同时处理多个回调。事件不擅长处理异步操作。

Promise 是以最简单的方式处理异步操作的理想选择。它们可以轻松处理多个异步操作，并提供比回调和事件更好的错误处理。换句话说，我们可以说，Promise 是同时处理多个回调的理想选择，从而避免了不希望的回调地狱情况。Promise 确实为用户提供了一个更好的机会，以更有效的方式阅读代码，尤其是当特定代码用于实现多个异步操作时。

## Promise 的好处

1.  提高代码可读性
2.  更好地处理异步操作
3.  异步逻辑中更好的控制定义流程
4.  更好的错误处理

## Promise 的四种状态

1.  **履行 (Fulfilled)**: 与 Promise 相关的行动成功。
2.  **拒绝 (Rejected)**: 与 Promise 相关的行动失败。
3.  **待定 (Pending)**: Promise 仍然待定，即尚未履行或拒绝。
4.  **已结算 (Settled)**: Promise 已履行或已拒绝。

## 创建 Promise

可以使用 `Promise` 构造函数创建 Promise。

### 语法

```javascript
var promise = new Promise(function(resolve, reject){
     //do something
});
```

### 参数

*   `Promise` 构造函数只接受一个参数，即回调函数（该回调函数也被称为匿名函数）。
*   回调函数接受两个参数，`resolve` 和 `reject`。
*   在回调函数中执行操作，如果一切顺利，就调用 `resolve`。
*   如果所需操作不顺利，则调用 `reject`。

## 示例

```javascript
var promise = new Promise(function(resolve, reject) {
  const x = "geeksforgeeks";
  const y = "geeksforgeeks"
  if(x === y) {
    resolve();
  } else {
    reject();
  }
});

promise.
    then(function () {
        console.log('Success, You are a GEEK');
    }).
    catch(function () {
        console.log('Some error has occurred');
    });
```

**输出:**

```
Success, You are a GEEK
```

## Promise 消费者

使用 `then()` 和 `catch()` 方法即可消费 Promise。

### 1. then()

当 Promise 被解决或拒绝时，就会调用 `then()`。它也可以被定义为从 Promise 中获取数据并进一步成功执行的链。

#### 参数

`then()` 方法取两个函数作为参数。

1.  如果 Promise 得到解决并收到结果，则执行第一个函数。
2.  如果拒绝 Promise 并收到错误，则执行第二个函数。（可选，使用 `catch()` 有更好的处理错误的方法。）

#### 语法

```javascript
.then(function(result){
        //handle success
    }, function(error){
        //handle error
    })
```

#### 示例：Promise 已解决

```javascript
var promise = new Promise(function(resolve, reject) {
    resolve('Geeks For Geeks');
})

promise
    .then(function(successMessage) {
       //success handler function is invoked
        console.log(successMessage);
    }, function(errorMessage) {
        console.log(errorMessage);
    })
```

**输出:**

```
Geeks For Geeks
```

#### 示例：Promise 被拒绝

```javascript
var promise = new Promise(function(resolve, reject) {
    reject('Promise Rejected')
})

promise
    .then(function(successMessage) {
        console.log(successMessage);
    }, function(errorMessage) {
       //error handler function is invoked
        console.log(errorMessage);
    })
```

**输出:**

```
Promise Rejected
```

### 2. catch()

当 Promise 被拒绝或执行中出现错误时，调用 `catch()`。只要在任何一步有可能出错，它就被用作错误处理程序。

#### 参数

`catch()` 方法以一个函数为参数。

1.  处理错误或拒绝 Promise 的函数。（`.catch()` 方法在内部调用 `.then(null, errorHandler)`，即 `.catch()` 只是 `.then(null, errorHandler)` 的语法糖。）

#### 语法

```javascript
.catch(function(error){
        //handle error
    })
```

#### 示例：Promise 被拒绝

```javascript
var promise = new Promise(function(resolve, reject) {
    reject('Promise Rejected')
})

promise
    .then(function(successMessage) {
        console.log(successMessage);
    })
    .catch(function(errorMessage) {
       //error handler function is invoked
        console.log(errorMessage);
    });
```

**输出:**

```
Promise Rejected
```

#### 示例：执行中抛出错误

```javascript
var promise = new Promise(function(resolve, reject) {
    throw new Error('Some error has occurred')
})

promise
    .then(function(successMessage) {
        console.log(successMessage);
    })
    .catch(function(errorMessage) {
       //error handler function is invoked
        console.log(errorMessage);
    });
```

**输出:**

```
Error: Some error has occurred
```

## 应用

1.  Promise 用于事件的异步处理。
2.  Promise 用于处理异步 HTTP 请求。

## 参考

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

JavaScript 最出名的是网页开发，但它也用于各种非浏览器环境。您可以通过以下 [JavaScript 教程](https://www.geeksforgeeks.org/javascript-tutorial/)和 [JavaScript 示例](https://www.geeksforgeeks.org/javascript-examples/)从头开始学习 JavaScript。