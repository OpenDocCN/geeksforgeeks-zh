# Node.js assert.doesNotThrow() 函数

> 原文: [https://www.geeksforgeeks.org/node-js-assert-doesnotthrow-function/](https://www.geeksforgeeks.org/node-js-assert-doesnotthrow-function/)

`assert` 模块提供了一组用于验证不变量的断言函数。`assert.doesNotThrow()` 函数断言函数 `fn` 不会抛出错误。

## 语法

```js
assert.doesNotThrow(fn[, error][, message])
```

## 参数

该功能接受如下参数：

*   `fn`: 这个参数是一个不会抛出错误的函数。
*   `error`: 此参数是正则表达式或函数。这是指定的错误。这是一个可选参数。
*   `message`: 此参数保存字符串或错误类型的错误消息。这是一个可选参数。

## 返回值

该函数返回对象类型的断言错误。

## 安装 assert 模块

1.  您可以访问链接 [Install assert module](https://www.npmjs.com/package/assert)。可以使用以下命令安装此包。

```js
npm install assert
```

**注意:** 安装是可选步骤，因为它内置了 Node.js 模块。

2.  安装 `assert` 模块后，您可以使用命令在命令提示符下检查您的 `assert` 版本。

```js
npm version assert
```

3.  之后，您可以创建一个文件夹并添加一个文件，例如 `index.js`，如下所示。

### 示例 1: 文件名: index.js

```js
// Requiring the module
const assert = require('assert').strict;

// Function call
try {
    assert.doesNotThrow(
        () => {
          throw new TypeError('Wrong value');
        },
    );
} catch(error) {
    console.log("Error:", error)
}
```

**运行程序的步骤:**

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令运行 `index.js` 文件：

```js
node index.js
```

**输出:**

> Error: AssertionError [ERR_ASSERTION]: Got unwanted exception.
> Actual message: "Wrong value"
>     at Object.<anonymous> (C:\Users\Lenovo\Downloads\index.js:6:12)
>     at Module._compile (internal/modules/cjs/loader.js:1138:30)
>     at Object.Module._extensions..js (internal/modules/cjs/loader.js:1158:10)
>     at Module.load (internal/modules/cjs/loader.js:986:32)
>     at Function.Module._load (internal/modules/cjs/loader.js:879:14)
>     at Function.executeUserEntryPoint [as runMain] (internal/modules/run_main.js:71:12)
>     at internal/main/run_main.js:71:12

### 示例 2: 文件名: index.js

```js
// Requiring the module
const assert = require('assert').strict;

// Function call
try {
    assert.doesNotThrow(
        () => {
          throw new TypeError('The Wrong value error');
        },
        /abcd/,
        'Whoops'
    );
} catch(error) {
    console.log("Error:", error)
}
```

**运行程序的步骤:**

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令运行 `index.js` 文件：

```js
node index.js
```

**输出:**

> Error: TypeError: The Wrong value error
>     at getActual (Assert.js:657:5)
>     at Function.doesNotThrow (Assert.js:805:32)
>     at Object.<anonymous> (C:\Users\Lenovo\Downloads\geeksforgeeks internship\NEW\Assert\index.js:6:12)
>     at Module._compile (internal/modules/cjs/loader.js:1138:30)
>     at Object.Module._extensions..js (internal/modules/cjs/loader.js:1158:10)
>     at Module.load (internal/modules/cjs/loader.js:986:32)
>     at Function.Module._load (internal/modules/cjs/loader.js:879:14)
>     at Function.executeUserEntryPoint [as runMain] (internal/modules/run_main.js:71:12)

**参考:** [https://nodejs.org/dist/latest-v12.x/docs/api/assert.html#assert_assert_doesnotthrow_fn_error_message](https://nodejs.org/dist/latest-v12.x/docs/api/assert.html#assert_assert_doesnotthrow_fn_error_message)