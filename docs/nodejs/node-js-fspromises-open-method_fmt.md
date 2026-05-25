# Node.js `fsPromises.open()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-fspromises-open-method/](https://www.geeksforgeeks.org/node-js-fspromises-open-method/)

`fsPromises.open()` 方法用于异步打开一个文件，该文件返回一个 `Promise`，解析后产生一个 `FileHandle` 对象。

## 语法

```js
fsPromises.open( filename, flags, mode)
```

## 参数

该方法接受三个参数，如下所述：

*   **File name:** 它是一个字符串、Buffer或Web地址，包含要读取文件的名称或完整路径（如果存储在其他位置）。
*   **Flag:** 它是一个字符串或数字，指定文件必须进行的操作。默认为 `"r"`。
*   **mode:** 是一个字符串或整数。设置文件模式，即 `r`：读取，`w`：写入，`r+`：读写。默认设置为读写。

## 返回值

返回一个 `Promise`。

下面的例子说明了 Node.js 中的 `fsPromises.open()` 方法：

## 例

```js
// Node.js program to demonstrate the     
// fsPromises.open() Method

// Include the fs module 
var fs = require('fs'); 
var fsPromises = fs.promises;

// Open file Demo.txt in read mode 
fsPromises.open('Demo.txt', 'r')
.then((result)=>{
    console.log(result);
})
.catch((error)=>{
    console.log(error);
});
```

## 输出

```js
FileHandle { [Symbol(handle)]: FileHandle { fd: 3 } }
```

## 说明

文件被打开，标志设置为读取模式。打开文件后，调用函数读取文件内容并存储在内存中。

## 注意

`mode` 设置文件模式（权限和粘性位），但前提是文件是创建的。

部分字符（`<`、`>`、`:`、`/`、`\`、`|`、`?`、`*`）保留在 Windows 下，如命名文件、路径和命名空间所记录的。