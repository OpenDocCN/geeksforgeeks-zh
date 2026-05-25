# JavaScript 中的 Promise.reject() 与 throw 语句

> 原文：[https://www.geeksforgeeks.org/reject-vs-throw-promises-in-javascript/](https://www.geeksforgeeks.org/reject-vs-throw-promises-in-javascript/)

本文介绍了 JavaScript 中 `reject()` 和 `throw` 的用法，并解释了它们的区别。

## Promise.reject()

`Promise.reject()` 是 JavaScript 中的一个内置函数，它返回一个被拒绝的 `Promise` 对象。

**语法：**

```javascript
Promise.reject(reason)
```

**示例：** `reason` 可以是简单的字符串消息，或者您甚至可以传递一个 `Error` 对象。

*   **程序 1：** 传递字符串消息作为 `reason`。

```javascript
const p = new Promise( ( resolve, reject ) => {

   reject( 'promise failed!' );

});
p.catch(err => {

    console.log( err );

});
```

*   **输出：**

```
promise failed!
```

*   **程序 2：** 传递 `Error` 实例作为 `reason`。

```javascript
const p = new Promise( ( resolve, reject ) => {

   reject( new Error( 'promise failed!' ) );

});
p.catch( err => {

    console.log( err );

});
```

*   **输出：** 如您所见，当我们传递一个 `Error` 对象时，我们得到了完整的错误堆栈。因此，用户更喜欢哪一个取决于用户。

```
Error: promise failed!
    at :4:9
    at new Promise ()
    at :2:11
    at render (tryit.php:202)
    at tryit.php:170
    at dispatch (jquery.js:4435)
    at r.handle (jquery.js:4121)
```

## throw 语句

`throw` 语句在 JavaScript 中用于创建和抛出用户定义的异常。使用 `throw` 语句，可以完全控制程序流程并生成用户定义的错误消息。如果我们在上面两个例子中用 `throw` 代替 `reject()`，结果会完全一样（你可以直接用 `throw` 代替 `reject` 自己试试）。

**举例：** 然而 `throw` 可以用在任何一个 JavaScript `try...catch` 块中，而不能只用于 `Promise`。

*   **程序 1：** 在 `Promise` 中使用 `throw`。

```javascript
const p = new Promise( ( resolve, reject ) => {

   throw( 'promise failed!' );

});
p.catch(err => {

    console.log( err );

});
```

*   **输出：**

```
promise failed!
```

*   **程序 2：** 在非 `Promise` 场景中使用 `throw`。

```javascript
var a = 20;
try
{
  if( a < 25 )

    throw ( 'Less than 25' );

  console.log( 'Okay!' );
}
catch(err)
{
  console.log( err );
}
```

*   **输出：**

```
Less than 25
```

## Promise.reject() 与 throw 的比较

现在我们已经了解了 `reject()` 和 `throw` 的基本工作原理，让我们来谈谈它们之间的区别：

**1. 在异步回调中的行为：** 如果在 `Promise` 中有一个异步回调函数，那么我们**不能**在回调函数中使用 `throw`，因为它将不会被 `catch()` 识别，并且我们将在输出中得到一个未捕获的错误。

*   **程序 1：**

```javascript
const p = new Promise( ( resolve, reject ) => {

    // Asynchronous function called within the Promise.
    setTimeout( () => { 
      throw( 'promise failed!' );

    }, 1000);
  });

  // The catch block will not be able to recognize the
  // error thrown. It will become an uncaught exception.
  p.catch( ( err )=> {

    console.log( err );
  });
```

*   **输出：** 如你所见，错误信息（`"promise failed!"`）已在输出中打印，但不是通过我们 `Promise` 的 `catch()` 功能打印的。它成为一个未捕获的异常。

```
/home/akarshan/Desktop/Projects/Personal/gfg/app.js:3
      throw( 'promise failed!' );
      ^
promise failed!
(Use `node --trace-uncaught ...` to show where the exception was thrown)
```

*   **程序 2：** 为了解决上述情况，我们可以使用 `reject()` 方法。

```javascript
const p = new Promise( ( resolve, reject ) => {

    // Asynchronus function called within the Promise.
    setTimeout( () => {

      reject( 'promise failed!' );

    }, 1000);
  });

  // The catch block will be able to recognize
  // the rejected statement.
  p.catch( (err) => {

    console.log( err );
  });
```

*   **输出：** 这里 `catch` 块能够识别 `reject()` 并打印相应的消息。

```
promise failed!
```

**2. 对控制流的影响：** 这是一个非常基本的区别。如果在函数内的任何地方遇到 `throw`，则立即抛出异常，并且控制流程终止。换句话说，在抛出异常之后，控制从抛出异常的函数中出来。

*   **程序 1：**

```javascript
const p = new Promise( ( resolve, reject ) => {

      throw( 'promise failed!' );     

      console.log("Here");
  });

p.catch( err => {
    console.log( err )
});
```

*   **输出：** 从这个例子中可以清楚地看到，语句 `console.log("Here")` 没有被执行。

```
'promise failed!'
```

*   **程序 2：** 为了解决上述情况，我们使用 `reject()` 代替 `throw`。函数中 `reject` 语句之后的语句将在控件进入 `catch` 块之前被执行。

```javascript
const p = new Promise( ( resolve, reject ) => {

      reject( 'promise failed!' );     

      console.log( "Here" );
  });

p.catch( err => {

    console.log( err )
});
```

*   **输出：**

```
Here
promise failed!
```

**3. 适用范围：** `Promise.reject()` 只能与 JavaScript `Promise` 一起使用，但是 `throw` 与 `reject` 不同，可以用于在任何 `try...catch` 块中创建和抛出用户定义的异常，而不仅仅是带有 `Promise` 的场景。如果在不与 `Promise` 相关联的 `try...catch` 块中使用 `Promise.reject()`，将弹出 `UnhandledPromiseRejection` 警告错误。

*   **程序 1：**

```javascript
var a=20;

try{

if( a < 25 )

   Promise.reject ( 'Less than 25' );

console.log( 'Okay!' );
}
catch(err)
{
  console.log( "inside catch" );

  console.log( err );
}
```

*   **输出：** 在这里，`UnhandledPromiseRejection` 警告错误出现，因为 `Promise.reject()` 找不到与 `Promise` 对象相关联的捕获块。

```
Okay!
```

*   **程序 2：** 上述代码中的 `catch` 块与任何 `Promise` 对象都没有关联，因此不执行。这一点从输出中可以清楚地看到，因为 `"inside catch"` 的信息没有被打印出来。但是如果我们使用 `throw`，这个错误就不会发生。

```javascript
var a=20;

try{

if( a < 25 )

  throw ( 'Less than 25' );

console.log( 'Okay!' );

}
catch(err)
{
  console.log( "inside catch" );

  console.log( err );
}
```

*   **输出：**

```
inside catch
Less than 25
```