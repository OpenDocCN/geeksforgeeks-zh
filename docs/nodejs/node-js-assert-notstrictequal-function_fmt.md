# Node.js assert.notStrictEqual() 函数

> 原文: [https://www.geeksforgeeks.org/node-js-assert-notstrictequal-function/](https://www.geeksforgeeks.org/node-js-assert-notstrictequal-function/)

`assert` 模块提供了一组用于验证不变量的断言函数。`assert.notStrictEqual()` 函数测试实际参数和预期参数之间的严格不等式。如果条件为真，则不会产生输出，否则会引发断言错误。

## 语法

```js
assert.notStrictEqual(actual, expected[, message])
```

## 参数

该功能有三个参数，`actual` 参数为任意类型，`expected` 参数为任意类型，`message` 参数可以为字符串或错误类型。

## 返回值

此函数返回对象类型的断言错误。

## 安装 assert 模块

1.  您可以访问[安装 assert 模块](https://www.npmjs.com/package/assert)的链接。您可以使用此命令安装此软件包。

    ```js
    npm install assert
    ```

2.  **注意:** 安装是可选步骤，因为它内置了 Node.js 模块。
3.  安装 assert 模块后，您可以使用命令在命令提示符下检查您的 `assert` 版本。

    ```js
    npm version assert
    ```

4.  之后，您可以创建一个文件夹并添加一个文件，例如 `index.js`，如下所示。

## 示例 1

**文件名:** `index.js`

```js
// Requiring the module
const assert = require('assert').strict;

var a = 2;
var b = 2;

// Function call
try {
    assert.notStrictEqual(a, b)
} catch(error) {
    console.log("Error: ", error)
}
```

### 运行程序的步骤

1.  项目结构会是这样的: ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令运行 `index.js` 文件:

    ```js
    node index.js
    ```

3.  **输出:**

    > Error: AssertionError [ERR_ASSERTION]: Expected "actual" to strictly not be equal to: 2
    >     at Object.<anonymous> (C:\Users\Lenovo\Downloads\index.js:9:12)
    >     at Module._compile (internal/modules/cjs/loader.js:1138:30)
    >     at Object.Module._extensions..js (internal/modules/cjs/loader.js:1158:10)
    >     at Module.load (internal/modules/cjs/loader.js:986:32)
    >     at Function.Module._load (internal/modules/cjs/loader.js:879:14)
    >     at Function.executeUserEntryPoint [as runMain] (internal/modules/run_main.js:71:12)
    >     at internal/main/run_main.js:15:5

## 示例 2

**文件名:** `index.js`

```js
// Requiring the module
const assert = require('assert').strict;

var a = 4;
var b = "Four";

// Function call
try {
    assert.notStrictEqual(a, b)
    console.log("No Error Occured")
} catch(error) {
    console.log("Error: ", error)
}

a = 4;
b = 4;

// Function call
try {
    assert.notStrictEqual(a, b)
} catch(error) {
    console.log("Error Occured: ", error)
}
```

### 运行程序的步骤

1.  项目结构会是这样的: ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令运行 `index.js` 文件:

    ```js
    node index.js
    ```

3.  **输出:**

    > No Error Occured
    > Error Occured: AssertionError [ERR_ASSERTION]: Expected "actual" to strictly not be equal to: 4
    >     at Object.<anonymous> (C:\Users\Lenovo\Downloads\index.js:20:12)
    >     at Module._compile (internal/modules/cjs/loader.js:1138:30)
    >     at Object.Module._extensions..js (internal/modules/cjs/loader.js:1158:10)
    >     at Module.load (internal/modules/cjs/loader.js:986:32)
    >     at Function.Module._load (internal/modules/cjs/loader.js:879:14)
    >     at Function.executeUserEntryPoint [as runMain] (internal/modules/run_main.js:71:12)
    >     at internal/main/run_main.js:15:5

## 参考

[https://nodejs.org/dist/latest-v12.x/docs/api/assert.html#assert_assert_notstrictequal_actual_expected_message](https://nodejs.org/dist/latest-v12.x/docs/api/assert.html#assert_assert_notstrictequal_actual_expected_message)