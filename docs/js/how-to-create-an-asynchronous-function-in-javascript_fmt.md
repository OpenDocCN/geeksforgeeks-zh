# 如何用 Javascript 创建异步函数？

> 原文：[https://www.geeksforgeeks.org/how-to-create-an-asynchronous-function-in-javascript/](https://www.geeksforgeeks.org/how-to-create-an-asynchronous-function-in-javascript/)

JavaScript 是单线程和同步语言。代码一次按一个顺序执行。但是在某些情况下，Javascript 可能看起来是异步的。

**示例：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <title></title>
</head>
<body>
    <div id="message"></div>
    <script>
        var msg = document.getElementById("message");

        function f1() {
            setTimeout(function () {
                msg.innerHTML += "<p>f1 is starting</p>";
                msg.innerHTML += "<p>f1 is ending</p>";
            }, 100);
        }
        function f2() {
            msg.innerHTML += "<p>f2 is starting</p>";
            f1();
            msg.innerHTML += "<p>f2 is ending</p>";
        }

        f2();
    </script>
</body>
</html>
```

**输出**

```
f2 is starting
f2 is ending
f1 is starting
f1 is ending
```

现在，我们可以看到在执行 `setTimeout(f1, 100)` 之后，我们的程序并没有等待计时器完成它，而是立即跳到下一条语句。发生这种情况是因为如果我们想要执行某个事件，JavaScript 会将该事件放入事件队列，并继续程序的正常执行。引擎定期在事件队列中查看是否需要调用某个事件。

但是我们可能希望我们的程序等到某个特定的事件或工作完成后再处理进一步的命令。

异步函数使用 `async`、`await` 和 `Promise` 来实现。

*   **async：** `async` 关键字定义了一个异步函数。

    ```javascript
    Syntax
    async function FunctionName(){
        ...
    }
    ```

*   **await：** `async` 函数包含暂停 `async` 函数执行的 `await`。`await` 只在 `async` 函数中有效。
*   **Promise：** `Promise` 是一个代理值。它告诉我们异步事件的成功/失败。`Promise` 必须包含 `resolve()` 或 `reject()` 调用，否则 `Promise` 的消费者将永远不知道承诺是否得到履行。如果发生这种情况，那么程序将继续等待，该代码块将永远不会被进一步执行。`Promise` 还有很多，但是我们可以在没有任何深入知识的情况下实现异步功能。

## 使用 async/await 和 Promise

**示例：** 让我们使用异步函数重做上面的示例。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <title></title>
</head>
<body>
    <div id="message"></div>
    <script>
        var msg = document.getElementById("message");

        function f1() {
            return new Promise(function (resolve, reject) {
                setTimeout(function () {
                    msg.innerHTML += "<p>f1 is starting</p>";
                    msg.innerHTML += "<p>f1 is ending</p>";
                    resolve();
                }, 100);
            })
        }

        async function f2() {
            msg.innerHTML += "<p>f2 is starting</p>";

            // Engine waits for f1() to finish it's 
            // execution before executing the next line
            await f1(); 
            msg.innerHTML += "<p>f2 is ending</p>";
        }

        f2();
    </script>
</body>
</html>
```

**输出：**

```
f2 is starting
f1 is starting
f1 is ending
f2 is ending
```

在上面的示例中，程序等待 `f1()` 完成执行，然后继续下一步。`await` 停止该代码段的执行，直到收到一个 `Promise`。`resolve()` 用于解析 `Promise`。这意味着 `Promise` 实现了。与 `resolve` 类似，我们也可以使用 `reject()` 来知道 `Promise` 被拒绝。`reject()` 函数主要用于调试和错误目的，我们现在不需要深入挖掘。

**示例：** 如果我们希望 `Promise` 返回一些值，我们可以将其传递给 `resolve(variable)`。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <title></title>
</head>
<body>
    <div id="message"></div>
    <script>
        var msg = document.getElementById("message");

        function f1() {
            return new Promise(function (resolve, reject) {
                setTimeout(function () {
                    msg.innerHTML += "<p>f1 is starting</p>";
                    msg.innerHTML += "<p>f1 is ending</p>";
                    resolve(1);
                }, 100);
            })
        }

        async function f2() {
            msg.innerHTML += "<p>f2 is starting</p>";
            var p = await f1();
            if (p == 1) msg.innerHTML += "<p>Promise Recieved</p>"
            msg.innerHTML += "<p>f2 is ending</p>";
        }

        f2();
    </script>
</body>
</html>
```

**输出：**

```
f2 is starting
f1 is starting
f1 is ending
Promise Received
f2 is ending
```

## 等待多个 Promise

如果我们必须等待多个功能会怎样？我们有两种方法。

**示例：** 我们可以按顺序编写多个 `await` 语句。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <title></title>
</head>
<body>
    <div id="message"></div>
    <script>
        var msg = document.getElementById("message");

        function f1() {
            return new Promise(function (resolve, reject) {
                setTimeout(function () {
                    msg.innerHTML += "<p>f1 is starting</p>";
                    msg.innerHTML += "<p>f1 is ending</p>";
                    resolve();
                }, 1000);
            })
        }

        function f3() {
            return new Promise(function (resolve, reject) {
                setTimeout(function () {
                    msg.innerHTML += "<p>f3 is starting</p>";
                    msg.innerHTML += "<p>f3 is ending</p>";
                    resolve();
                }, 1000);
            })
        }

        async function f2() {
            msg.innerHTML += "<p>f2 is starting</p>";
            await f1();
            await f3();
            msg.innerHTML += "<p>f2 is ending</p>";
        }

        f2();
    </script>
</body>
</html>
```

**输出**

```
f2 is starting
f1 is starting
f1 is ending
f3 is starting
f3 is ending
f2 is ending
```

在上面的例子中，首先我们得到 `f2 is starting`，1 秒钟后我们得到 `f1 is starting` 和 `f1 is ending`，然后再过 1 秒钟，我们得到 `f3 is starting`、`f3 is ending` 和 `f2 is ending`。

**示例：** 等待多个 `Promise` 的第二种方法是使用 `Promise.all(iterable)` 并行运行 `Promise`。

**语法：**

```javascript
await Promise.all(iterable);
```

**示例：**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <title></title>
</head>
<body>
    <div id="message"></div>
    <script>
        var msg = document.getElementById("message");

        function f1() {
            return new Promise(function (resolve, reject) {
                setTimeout(function () {
                    msg.innerHTML += "<p>f1 is starting</p>";
                    msg.innerHTML += "<p>f1 is ending</p>";
                    resolve();
                }, 1000);
            })
        }

        function f3() {
            return new Promise(function (resolve, reject) {
                setTimeout(function () {
                    msg.innerHTML += "<p>f3 is starting</p>";
                    msg.innerHTML += "<p>f3 is ending</p>";
                    resolve();
                }, 1000);
            })
        }

        async function f2() {
            msg.innerHTML += "<p>f2 is starting</p>";
            await Promise.all([f1(), f3()]);
            msg.innerHTML += "<p>f2 is ending</p>";
        }

        f2();
    </script>
</body>
</html>
```

**输出**

```
f2 is starting
f1 is starting
f1 is ending
f3 is starting
f3 is ending
f2 is ending
```

输出与之前的代码相同，但在这种情况下，程序会输出 `f2 is starting`，然后等待 1 秒，输出 `f1 is starting`、`f1 is ending`、`f3 is starting`、`f3 is ending` 和 `f2 is ending`。

由于 `f1()` 和 `f3()` 是并行运行的，我们不需要再等 1 秒钟就可以执行 `f3()`。简单来说，`f1()` 和 `f3()` 中 `setTimeout()` 的定时器同时启动。

**注意：** 我们也可以只使用 `Promises` 实现异步行为，而不使用 `async/await` 和回调，请参考以下链接：

*   [https://www.geeksforgeeks.org/javascript-callbacks/](https://www.geeksforgeeks.org/javascript-callbacks/)
*   [https://www.geeksforgeeks.org/javascript-promises/](https://www.geeksforgeeks.org/javascript-promises/)