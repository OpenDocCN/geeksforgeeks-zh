# Node.js | script.runInThisContext() 方法

> 原文：[https://www.geeksforgeeks.org/node-js-script-runinthiscontext-method/](https://www.geeksforgeeks.org/node-js-script-runinthiscontext-method/)

该方法在虚拟机的上下文中运行编译后的代码，即当前全局对象的上下文。此外，运行的代码无法访问本地作用域，但可以访问当前的全局对象。

## 语法

```js
script.runInThisContext( options )
```

## 参数

该方法接受单个可选参数 `options`，返回一个 `Object`。选项包括 `displayErrors`、`timeout` 和 `breakOnFirstLine`。

## 返回值

返回脚本中最后一条语句的执行结果。

## 示例

下面的例子说明了在 Node.js 中使用 `script.runInThisContext()` 方法：

### 例 1

```js
// Node.js program to demonstrate the     
// script.runInThisContext() method

// Including vm module
const vm = require('vm');

// Defining code
let code = 'console.log("I am an author?");';

// Defining script
let script = new vm.Script(code);

// Calling runInThisContext method
script.runInThisContext();
```

**输出：**

```js
I am an author?
```

### 例 2

```js
// Node.js program to demonstrate the     
// script.runInThisContext() method

// Including vm module
const vm = require('vm');

// Defining x and y
var x = 40; var y = 17;

// Adding x and y
const z = x + y;

// Defining code
let code = `console.log(${z})`;

// Defining script
let script = new vm.Script(code);

// Calling runInThisContext method
script.runInThisContext();
```

**输出：**

```js
57
```

## 参考

[https://nodejs.org/api/vm.html#vm_script_runinthiscontext_options](https://nodejs.org/api/vm.html#vm_script_runinthiscontext_options)