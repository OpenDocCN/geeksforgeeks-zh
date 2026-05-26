# Underscore.js `_.methodize()`方法

> 原文：[https://www.geeksforgeeks.org/underscore-js-_-methodize-method/](https://www.geeksforgeeks.org/underscore-js-_-methodize-method/)

`_.methodize()`方法接受一个函数，将第一个参数从参数列表中移出，放入`this`的位置。返回的函数调用原始函数，其接收者（`this`）被置于参数列表的前面。

**语法：**

```javascript
_.methodize( function );
```

**参数：** 该方法接受如上所述的单个参数，如下所述：

*   `function`：包含参数的原始函数。

**返回值：** 该方法返回一个函数。

**注意：** 这在标准的JavaScript中无法工作，因为它需要安装Underscore.js contrib库。

可以使用`npm install underscore-contrib --save`来安装Underscore.js contrib库。

**例1：**

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

function gfgFunc (obj) {
    return obj.name + ": " + obj.about;
}

var Geeks = {
    name: "GeeksforGeeks",
    about: "Computer Science Portal for Geeks",
    fun: _.methodize(gfgFunc)
};

console.log(Geeks.fun())
```

**输出：**

```
GeeksforGeeks: Computer Science Portal for Geeks
```

**例2：**

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib');

function gfgFunc (obj) {
    return "Geeks";
}

fun= _.methodize(gfgFunc)
console.log(fun())
```

**输出：**

```
Geeks
```