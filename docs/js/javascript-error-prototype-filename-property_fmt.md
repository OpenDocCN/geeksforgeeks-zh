# JavaScript Error.prototype.fileName 属性

> 原文：[https://www.geeksforgeeks.org/javascript-error-prototype-filename-property/](https://www.geeksforgeeks.org/javascript-error-prototype-filename-property/)

`fileName` 是一个非标准属性，包含引发此[错误](https://www.geeksforgeeks.org/javascript-errors-throw-and-try-to-catch/)的文件路径。建议不要在面向 Web 的生产站点上使用此属性，因为它可能不适用于每个用户。如果从火狐开发工具中调用，将返回“调试器评估代码”。该属性是参数之一，在[创建错误对象](https://www.geeksforgeeks.org/javascript-error-constructor/)时传递。

**语法：**

```
errorObj.fileName
```

**属性值：** 包含引发此错误的代码的文件的路径。

**返回值：** 它返回一个字符串，表示包含引发此错误的代码的文件的路径。

**示例 1：**

```javascript
try {
    var err = new Error("Could not parse file");
    if(err.fileName == undefined)
        err.fileName = "/Users/abhinavjain194/desktop/GFG/err.js"
    throw err;
}
catch(e) {
    console.log("Error: " + e.message);
    console.log("The Error occurred at " + e.fileName);
}
```

**输出：**

```
Error: Could not parse file
The Error occurred at /Users/abhinavjain194/desktop/GFG/err.js
```

**示例 2：**

```javascript
try {
    var err = new Error("Unexpected token output");
    if(err.fileName == undefined)
        err.fileName = 
            "/Users/abhinavjain194/desktop/GFG/token_err.js"
    throw err;
}
catch(e) {
    console.log("Error: " + e.message);
    console.log("The Error occurred at " + e.fileName);
}
```

**输出：**

```
Error: Unexpected token output
The Error occurred at /Users/abhinavjain194/desktop/GFG/token_err.js
```

**支持的浏览器：**

*   Google Chrome
*   Firefox
*   Safari
*   Opera
*   Microsoft Edge