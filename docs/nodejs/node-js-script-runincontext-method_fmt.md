# Node.js `script.runInContext()`方法

> 原文：[https://www.geeksforgeeks.org/node-js-script-runincontext-method/](https://www.geeksforgeeks.org/node-js-script-runincontext-method/)

方法用于运行存在于虚拟机中的编译代码。在所述上下文对象内编写对象的脚本并返回输出。但是，运行的代码无法访问本地范围。

## 语法

```js
script.runInContext( contextifiedObject, options )
```

## 参数

这个方法接受两个参数，如上所述，如下所述：

*   **`contextifiedObject`**：它是由 `vm.createContext()` 方法返回的一个上下文化对象。
*   **`options`**：是一个可选参数，返回对象。它包含以下参数：
    1.  **`displayErrors`**：它包含一个布尔值，即如果在编译代码时引发错误，并且导致错误的代码行链接到堆栈跟踪，则该值为 `true`。其默认值为 `true`。
    2.  **`timeout`**：它持有一个整数值，该值指定在结束执行之前执行代码所需的毫秒数。但是，如果执行被关闭，将会发生错误。此值必须是一个正整数。
    3.  **`breakOnSigint`**：它持有一个布尔值。如果为 `true`，则一旦提供 `SIGINT`（即 Ctrl+C），执行将停止，如果执行停止，将抛出一个错误。默认情况下，其值为 `false`。

## 返回值

返回脚本中最后一条语句的执行结果。

## 示例

下面的例子说明了在 Node.js 中 `script.runInContext()`方法的使用：

### 示例 1

```js
// Node.js program to demonstrate the     
// script.runInContext() method

// Including util and vm module
const util = require('util');
const vm = require('vm');

// Constructing context
const contextobj = {
  name: 'Nidhi',
  articles: 60
};

// Constructing script
const script = new vm.Script('articles *= 10;');

// Contextifying object
vm.createContext(contextobj);

// Calling runInContext method
script.runInContext(contextobj);

// Displays output
console.log(contextobj);
```

**输出：**

```js
{ name: 'Nidhi', articles: 600 }
```

这里，`articles` 是 600 as (60*10 = 600)。

### 示例 2

```js
// Node.js program to demonstrate the     
// script.runInContext() method

// Including util and vm module
const util = require('util');
const vm = require('vm');

// Constructing context
const contextobj = { globalVar: 6 };

// Constructing script
const script = new vm.Script('globalVar += 12;');

// Contextifying object
vm.createContext(contextobj);

// Calling for loop
for (let i = 1; i < 4; i++) {

// Calling runInContext method
script.runInContext(contextobj);
}

// Displays output
console.log("The output is: ", contextobj);
```

**输出：**

```js
The output is:  { globalVar: 42 }
```

## 参考

[https://nodejs.org/api/vm.html#vm_script_runincontext_contextifiedobject_options](https://nodejs.org/api/vm.html#vm_script_runincontext_contextifiedobject_options)