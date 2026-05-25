# Node.js `util.deprecate()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-util-deprecate-method/](https://www.geeksforgeeks.org/node-js-util-deprecate-method/)

`util.deprecate()`（在 v0.8.0 中添加）是 `util` 模块的内置应用程序编程接口，它以标记为弃用的方式包装 `fn`（可能是函数或类）。当调用 `util.deprecate()` 方法时，它返回一个使用“警告”事件发出弃用警告的函数。第一次调用返回的函数时，会发出警告并打印到 `stderr`。一旦发出警告，就调用包装函数。如果在对 `util.deprecate()` 的多次调用中提供了相同的可选代码，则仅发出一次警告。

## 语法

```js
util.deprecate(fn, msg, code)
```

## 参数

该函数接受三个参数，如下所述：

*   `fn`: 被弃用的函数。
*   `msg`: 当不推荐使用的功能被调用时，需要显示的“警告消息”字符串。
*   `code`: 是一个弃用代码字符串，与弃用警告一起打印。一些[不推荐使用的 API](https://nodejs.org/api/deprecations.html#deprecations_revoking_deprecations) 是 `DEP0001`，`DEP0002`，…，`DEP0143`。

## 返回值

返回包装后发出警告的弃用函数，即运行完整函数后，警告消息与弃用的 API 一起返回。

## 示例 1

**文件名:** `index.js`

```js
// Node.js program to demonstrate the
// util.deprecate() method

// Import the util module
var util = require('util');

var depricateFunction = util.deprecate(
    // Function which is depricated
    function () { },

    // Warning message that is
    // printed to stderr
    "someWarningMessage",

    // Deprecated API
    'Deprication API'
);

// Function call
depricateFunction();
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

```js
[Deprication API] DeprecationWarning: someWarningMessage
```

## 示例 2

**文件名:** `index.js`

```js
// Node.js program to demonstrate the
// util.deprecate() method

// Import the util module
var util = require('util');
var outerValue = "along with"

var geekyFunction1 = util.deprecate(() => {
    console.log("This Depricated function is working, ");
},
    // The arrow function which is depricated
    "geekyFunction() is deprecated. Use "
        + "geeksForGeeksFunction() instead",

    // The warning message that is printed
    // to stderr
    'DEP0014' // Deprecated API
);

var geekyFunction2 = util.deprecate(function (call) {
    console.log("This Depricated function is working, ",
            outerValue, call());
},
    // The function which is depricated
    "geekyFunction() is deprecated. Use "
        + "geeksForGeeksFunction() instead",
    // The warning message that is printed to stderr
    'DEP0014' // Deprecated API
);

// Function call
geekyFunction1();

// Function call
geekyFunction2(function call() {
    console.log("Callback");
    return "return value"
});
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

> This Depricated function is working,
> Callback
> This Depricated function is working, along with return value
> [DEP0014] DeprecationWarning: geekyFunction() is deprecated. Use geeksForGeeksFunction() instead

## 条件

*   如果为进程设置了 `--trace-deprecation` / `--trace-warnings` 命令行标志，则第一次将堆栈跟踪和警告打印到 `stderr`。`traceDeprecation` 属性设置为 `true`。
*   如果设置了 `--throw-deprecation` 命令行标志，或者 `process.throwDeprecation` 设置为 `true`，则会抛出异常。
*   如果将 `process.noDeprecation` 属性设置为 `true`，或者使用 `--no-deprecation` / `--no-warnings` 命令行标志，则 `util.deprecate()` 不执行任何操作。
*   `traceDeprecation` 和 `process.traceDeprecation` 的优先级低于 `--throw-deprecation` 命令行标志和 `process.throwDeprecation` 属性。

## 参考

[https://nodejs.org/api/util.html#util_util_deprecate_fn_msg_code](https://nodejs.org/api/util.html#util_util_deprecate_fn_msg_code)