# Node.js require 和 ES6 导入导出的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-node-js-require-and-es6-import-and-export/](https://www.geeksforgeeks.org/difference-between-node-js-require-and-es6-import-and-export/)

Node.js 遵循 CommonJS 模块系统，它使用 `require` 来包含存在于单独文件中的模块。而 `ES6 导入和导出` 则是另一种在 Node.js 中可用的模块化方法。

## Require

`require` 是一个内置函数，是包含独立文件中模块的最简单方法。`require` 的基本功能是读取一个 JavaScript 文件，执行该文件，然后返回导出的对象。它不仅允许您添加内置的核心 Node 模块，还允许您在程序中添加基于社区的模块（`node_modules`）和本地模块。Node.js 中有各种内置模块，例如 `HTTP 模块`、`URL 模块`、`查询字符串模块`、`路径模块` 等。

### 语法

*   内置模块的用法如下：

```javascript
const express = require('express');
```

*   包含本地模块的用法如下。例如，你需要 `abc` 模块，但不指定路径。

```javascript
require('abc');
```

### 示例

Node.js 将依次在 `module.paths` 指定的所有路径中查找模块。

*   **输入：**

```javascript
require('abc');
```

*   **输出：**
    *   **如果 Node 找不到：**

```
Error: Cannot find module 'abc'
    at Function.Module._resolveFilename (module.js:470:15)
    at Function.Module._load (module.js:418:25)
    at Module.require (module.js:498:17)
    at require (internal/module.js:20:19)
    at repl:1:1
    at ContextifyScript.Script.runInThisContext (vm.js:23:33)
    at REPLServer.defaultEval (repl.js:336:29)
    at bound (domain.js:280:14)
    at REPLServer.runBound [as eval] (domain.js:293:12)
    at REPLServer.onLine (repl.js:533:10)
```

*   **如果 Node 找到它：**

```javascript
// It is the content of the file
Geeksforgeeks example for require
```

## ES6 导入和导出

`import` 语句用于引用一个 ES 模块。其他文件类型不能用这些语句导入。它们仅在 ES 模块中被允许，并且该语句的说明符可以是 URL 样式的相对路径或包名。

而 `export` 语句允许用户将其创建的对象和方法导出到其他程序。例如，如果您分配了一个字符串文字，那么它会将该字符串文字公开为一个模块。

### 语法

*   用于导入文件。

```javascript
// Importing submodule from 
// 'es-module-package/private-module.js';
import './private-module.js';
```

*   用于导出文件。

```javascript
module.exports = 'A Computer Science Portal';
```

### 示例

创建两个 JS 文件，一个用于导出，另一个用于导入。或者您可以使用任何模块进行导入，这样就不需要单独的导出文件。

*   **导出**文件名 `Message.js`

```javascript
// Exporting module
module.exports = 'Hello Geek';
```

*   **导入**文件名 `Display.js`

```javascript
// Importing module
var msg = import('./Message.js');
console.log(msg);
```

*   **输出：**

```
Hello Geek
```

## Node.js require 和 ES6 导入导出的区别

虽然 `require` 函数和 ES6 `导入导出` 有很多共同点，在代码上看起来执行相同的功能，但是在很多方面是不同的。

| 特性 | require | ES6 导入和导出 |
| :--- | :--- | :--- |
| **性质** | `REQUIRE` 是非词法的，它停留在放置文件的位置。 | `Import` 是词法的，它会被提升到文件顶部。 |
| **调用时机** | 可以在程序中的任何地方、任何时间调用。 | 不能有条件地调用，总是在文件开头运行。 |
| **执行方式** | 可以直接使用 `require` 语句运行代码。 | 要运行包含 `import` 语句的程序，必须使用实验性模块功能标志。 |
| **文件扩展名** | 如果要使用 `require` 模块，必须使用 `.js` 扩展名保存文件。 | 如果要使用 `import` 模块，则必须使用 `.mjs` 扩展名保存文件。 |

**注意：** 您必须注意，在您的 Node 程序中不能同时使用 `require` 和 `import`。更优选使用 `require` 而不是 `import`，因为您需要使用实验性模块标志功能来运行包含 `import` 的程序。