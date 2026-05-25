# Node.js `console.trace()`方法

> 原文：[https://www.geeksforgeeks.org/node-js-console-trace-method/](https://www.geeksforgeeks.org/node-js-console-trace-method/)

`console.trace()`方法是控制台模块的内置应用编程接口，用于将堆栈跟踪消息以换行符的形式打印到`stderr`。类似于`console.error()`方法。

## 语法

```js
console.trace(message, args);
```

## 参数

该方法有两个参数，如上所述，描述如下：

1.  `message`：此参数指定要打印的消息。
2.  `args`：它是一个可选参数，指定要在消息中作为替换值传递的参数。所有传递的参数都被发送到`util.format()`。

## 返回值

这个方法不返回任何东西，只打印“Trace:”字符串，后跟一个换行符中的格式化消息到`stderr`，并堆栈跟踪到代码中的当前位置。

下面的例子说明了`console.trace()`方法在Node.js中的使用：

### 示例 1

**文件名：**`app.js`

```js
// Node.js program to demonstrate the 
// console.trace() method

// Accessing console module
const console = require('console');

// Calling console.trace() method
console.trace("stack teace sample");

console.trace(
    "stack trace sample with args: %d", 39);
```

使用以下命令运行`app.js`文件：

```bash
node app.js
```

**输出：**

> Trace: stack teace sample
>     at Object.<anonymous> (C:\nodejs\g\console\console_trace.js:4:9)
>     at Module._compile (internal/modules/cjs/loader.js:776:30)
>     at Object.Module._extensions..js (internal/modules/cjs/loader.js:787:10)
>     at Module.load (internal/modules/cjs/loader.js:653:32)
>     at Function.Module._load (internal/modules/cjs/loader.js:585:3)
>     at Function.Module.runMain (internal/modules/cjs/loader.js:829:12)
>     at startup (internal/bootstrap/node.js:283:19)
>     at bootstrapNodeJSCore (internal/bootstrap/node.js:622:3)
> Trace: stack trace sample with args: 39
>     at Object.<anonymous> (C:\nodejs\g\console\console_trace.js:5:9)
>     at Module._compile (internal/modules/cjs/loader.js:776:30)
>     at Object.Module._extensions..js (internal/modules/cjs/loader.js:787:10)
>     at Module.load (internal/modules/cjs/loader.js:653:32)
>     at Function.Module._load (internal/modules/cjs/loader.js:585:3)
>     at Function.Module.runMain (internal/modules/cjs/loader.js:829:12)
>     at startup (internal/bootstrap/node.js:283:19)
>     at bootstrapNodeJSCore (internal/bootstrap/node.js:622:3)

### 示例 2

**文件名：**`app.js`

```js
// Node.js program to demonstrate the 
// console.trace() method

// Accessing console module
const console = require('console');

// Calling console.trace() method
console.trace("stack trace message: "
    + "at %s: line no: %d ", "ff()", 96);

var isTrace = true;

console.custom_trace = function(message) {   
  if (isTrace) {
    console.trace(message);
  }
}

console.custom_trace("custom trace message");
```

使用以下命令运行`app.js`文件：

```bash
node app.js
```

**输出：**

> Trace: stack trace message: at ff(): line no: 96 
>     at Object.<anonymous> (C:\nodejs\g\console\console_trace_1.js:4:9)
>     at Module._compile (internal/modules/cjs/loader.js:776:30)
>     at Object.Module._extensions..js (internal/modules/cjs/loader.js:787:10)
>     at Module.load (internal/modules/cjs/loader.js:653:32)
>     at Function.Module._load (internal/modules/cjs/loader.js:585:3)
>     at Function.Module.runMain (internal/modules/cjs/loader.js:829:12)
>     at startup (internal/bootstrap/node.js:283:19)
>     at bootstrapNodeJSCore (internal/bootstrap/node.js:622:3)
> Trace: custom trace message
>     at console.custom_trace (C:\nodejs\g\console\console_trace_1.js:11:13)
>     at Object.<anonymous> (C:\nodejs\g\console\console_trace_1.js:14:9)
>     at Module._compile (internal/modules/cjs/loader.js:776:30)
>     at Object.Module._extensions..js (internal/modules/cjs/loader.js:787:10)
>     at Module.load (internal/modules/cjs/loader.js:653:32)
>     at Function.Module._load (internal/modules/cjs/loader.js:585:3)
>     at Function.Module.runMain (internal/modules/cjs/loader.js:829:12)
>     at startup (internal/bootstrap/node.js:283:19)
>     at bootstrapNodeJSCore (internal/bootstrap/node.js:622:3)

**注意：** 以上程序使用`node filename.js`命令编译运行。

**参考：** [https://nodejs.org/api/console.html#console_console_trace_data_args](https://nodejs.org/api/console.html#console_console_trace_data_args)