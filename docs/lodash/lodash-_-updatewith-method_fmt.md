# Lodash _.updateWith() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-updatewith-method/](https://www.geeksforgeeks.org/lodash-_-updatewith-method/)

`_.updateWith()` 方法接受一个定制函数，调用该函数来产生路径的对象。如果定制函数返回未定义的路径，则由方法来处理创建。它几乎和 `_.update()` 函数一样。

**语法:**

```
_.updateWith(object, path, updater, [customizer])
```

**参数:** 该方法接受上述四个参数，描述如下:

*   `object`: 此参数存储要修改的对象。
*   `path`: 此参数存储要设置的属性的路径。它将是一个数组或字符串。
*   `updater`: 这是一个生成更新值的函数。
*   `customizer`: 此参数存储自定义分配的函数。

**返回值:** 该方法返回对象。

**例 1:**

### JavaScript

```
// Requiring the lodash library
const _ = require("lodash");

// The source object
var obj = {};

// Use of _.updateWith() method
let gfg = _.updateWith(obj, '[0][1]',
    _.constant('y'), Object);

// Returning the new object
console.log(gfg);
```

**输出:**

```
{ '0': { '1': 'y' } }
```

**例 2:**

### JavaScript

```
// Requiring the lodash library
const _ = require("lodash");

// The source object
var obj = { 'cpp': [{ 'java': { 'python': 3 } }] };

// Use of _.updateWith() method
_.updateWith(obj, 'cpp[0].java.python',
    function(n) { return n * n; });

// Returning the updated object value
console.log(obj.cpp[0].java.python);
```

**输出:**

```
9
```

**注意:** 这在正常的 JavaScript 中不会起作用，因为它需要安装 lodash 库。