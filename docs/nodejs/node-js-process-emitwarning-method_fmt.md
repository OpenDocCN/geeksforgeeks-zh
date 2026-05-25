# Node.js process.emitWarning()方法

> 原文: [https://www.geeksforgeeks.org/node-js-process-emitwarning-method/](https://www.geeksforgeeks.org/node-js-process-emitwarning-method/)

`process.emitWarning()` 方法是 `process` 模块的内置应用程序编程接口，用于发送自定义或特定于应用程序的进程警告。

## 语法

```js
process.emitWarning(warning[, options])
```

## 参数

该函数接受以下参数：

*   `warning`: 用于表示将要发出的警告。
*   `options`: 是可选参数，可以有以下属性：
    *   `type`: 用于表示警告为字符串形式时发出的警告类型。
    *   `code`: 用于表示发出的警告实例的唯一标识符。
    *   `ctor`: 这是一个可选函数，用于在警告为字符串形式时限制生成的堆栈跟踪。
    *   `detail`: 用于添加要包含在错误中的附加文本。

## 返回值

此事件只返回一个回调函数，以便进一步操作。

## 示例

### 示例 1

`process.emitWarning()` 方法在监听进程的同时将错误对象传递给警告处理程序。

#### index.js

```js
console.log("Start ...");

// Use setInterval to keep the process running
setInterval(() => {
    console.log("Working ...");
}, 1000);

setTimeout(() => {
    process.emitWarning('Something happened!', {
        code: 'Custom_Warning',
        detail: 'Additional information about warning'
    });
}, 4000);

// Start listening to the process
process.on('warning', (warning) => {

// If there is a warning then print
    // it and stop the process
    if (warning) {
        console.log(warning);
        process.exit(0);
    }
});
```

使用以下命令运行 `index.js` 文件：

```js
node index.js
```

**输出：**

> Start ...
> Working ...
> Working ...
> Working ...
> (node:12621) [Custom_Warning] Warning: Something happened!
> Additional information about warning
> (Use `node --trace-warnings ...` to show where the warning was created)
> Warning: Something happened!
> Timeout._onTimeout (/home/aditya/Programming/GFG/New/emitwarning.js:9:13)
> at listOnTimeout (node:internal/timers:556:17)
> at processTimers (node:internal/timers:499:7) {
> code: 'Custom_Warning',
> detail: 'Additional information about warning'
> }

### 示例 2

发出多个警告，并根据警告类型采取措施。

#### index.js

```js
console.log("Start ...");

// Use setInterval to keep the process running
setInterval(() => {
    console.log("Working ...");
}, 1000);

setTimeout(() => {
    process.emitWarning('Something happened!', {
        code: 'Custom_Warning',
        detail: 'Additional information about warning'
    });
}, 4000);

setTimeout(() => {
    process.emitWarning('Something needs to be fixed!', {
        type: 'IMPORTANT',
        code: '007',
        detail: 'Can not proceed further!'
    });
}, 6000);

// Start listening to the process
process.on('warning', (warning) => {

// If there is an important warning
    // stop the process
    // warning.name = type
    if (warning.name === 'IMPORTANT') {
        console.log('Fix this ASAP!')
        process.exit(0);
    }
});
```

使用以下命令运行 `index.js` 文件：

```js
node index.js
```

**输出：**

> Start ...
> Working ...
> Working ...
> Working ...
> (node:12893) [Custom_Warning] Warning: Something happened!
> Additional information about warning
> (Use `node --trace-warnings ...` to show where the warning was created)
> Working ...
> Working ...
> (node:12893) [007] IMPORTANT: Something needs to be fixed!
> Can not proceed further!
> Fix this ASAP!

### 示例 3

将错误对象作为警告而不是字符串传递。请注意，如果正在传递错误对象，则可选参数将被忽略。

#### index.js

```js
console.log("Start ...");

// Use setInterval to keep the process running
setInterval(() => {
    console.log("Working ...");
}, 1000);

setTimeout(() => {
    process.emitWarning(new Error('Whoops!'), {
        code: 'Custom_Warning',
        detail: 'Additional information about warning'
    });
}, 4000);

// Start listening to the process
process.on('warning', (warning) => {

// If there is a warning then print
    // it and stop the process
    if (warning) {
        console.warn(warning);
        process.exit(0);
    }
});
```

使用以下命令运行 `index.js` 文件：

```js
node index.js
```

**输出：**

> Start ...
> Working ...
> Working ...
> Working ...
> (node:13232) Error: Whoops!
> (Use `node --trace-warnings ...` to show where the warning was created)
> Error: Whoops!
> Timeout._onTimeout (/home/aditya/Programming/GFG/New/emitwarning.js:9:25)
> at listOnTimeout (node:internal/timers:556:17)
> at processTimers (node:internal/timers:499:7)

## 参考

[https://nodejs.org/api/process.html#process_process_emitwarning_warning_type_code_ctor](https://nodejs.org/api/process.html#process_process_emitwarning_warning_type_code_ctor)