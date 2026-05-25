# Node.js assert.equal()函数

> 原文:[https://www.geeksforgeeks.org/node-js-assert-equal-function/](https://www.geeksforgeeks.org/node-js-assert-equal-function/)

`assert`模块提供了一组用于验证不变量的断言函数。`assert.equal()`函数测试实际参数和预期参数之间的相等性。如果条件为真，则不会产生输出，否则会引发断言错误。

## 语法:
```js
assert.equal(actual, expected[, message])
```

## 参数:
该功能接受如下参数，如上所述，如下所述:

*   `actual`: 此参数保存需要评估的实际值。它是任何类型的。
*   `expected`: 此参数保存与实际值匹配的预期值。它是任何类型的。
*   `message`: 此参数保存字符串或错误类型的错误消息。这是一个可选参数。

## 返回值:
该函数返回对象类型的断言错误。

## 安装 assert 模块:
1.  You can visit the link to [Install assert module](https://www.npmjs.com/package/assert). You can install this package by using this command.
    ```js
    npm install assert
    ```
    **注意:** 安装是可选步骤，因为它内置了 Node.js 模块。

2.  安装断言模块后，您可以使用命令在命令提示符下检查您的`assert`版本。
    ```js
    npm version assert
    ```

3.  之后，您可以创建一个文件夹并添加一个文件，例如`index.js`，如下所示。

## 示例 1:
**文件名:** `index.js`
```js
// Requiring the module
const assert = require('assert').strict;

var a = 10;
var b = 20;

// Function call
try {
    assert.equal(a, b);
} catch(error) {
    console.log("Error: ", error)
}
```

**运行程序的步骤:**
1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  Run `index.js` file using below command:
    ```js
    node index.js
    ```

**输出:**
> Error: AssertionError [ERR_ASSERTION]: Values have same structure but are not reference-equal:
> 
> 10 !== 20
> 
>     at Object.<anonymous> (C:\Users\Lenovo\Downloads\index.js:7:12)
>     at Module._compile (internal/modules/cjs/loader.js:1138:30)
>     at Object.Module._extensions..js (internal/modules/cjs/loader.js:1158:10)
>     at Module.load (internal/modules/cjs/loader.js:986:32)
>     at Function.Module._load (internal/modules/cjs/loader.js:879:14)
>     at Function.executeUserEntryPoint [as runMain] (internal/modules/run_main.js:71:12)
>     at internal/main/run_main.js:76:11

## 示例 2:
**文件名:** `index.js`
```js
// Requiring the module
const assert = require('assert').strict;

var a = 20;
var b = 20;

// Function call
try {
    assert.equal(a, b);
    console.log("No Error Occured")
} catch(error) {
    console.log("Error: ", error)
}
```

**运行程序的步骤:**
1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  Run `index.js` file using below command:
    ```js
    node index.js
    ```

**输出:**
```js
No Error Occured
```

**参考:** [https://nodejs.org/dist/latest-v12.x/docs/api/assert.html#assert_assert_equal_actual_expected_message](https://nodejs.org/dist/latest-v12.x/docs/api/assert.html#assert_assert_equal_actual_expected_message)