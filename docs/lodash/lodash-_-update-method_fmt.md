# 洛达什 _.update()方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-update-method/](https://www.geeksforgeeks.org/lodash-_-update-method/)

`_.update()`方法接受更新器产生的值进行设置。这个方法使用`_.`函数来自定义路径创建。几乎和`_.set()`函数。

## 语法

```
_.update(object, path, updater)
```

## 参数

该方法接受三个参数，如上所述，如下所述:

*   `object`: 此参数保存要修改的对象。
*   `path`: 此参数保存要设置的属性的路径。它将是数组或字符串。
*   `updater`: 这是产生更新值的函数。

## 返回值

该方法返回新对象。

**注意:** 这里，`const _ = require('lodash')`用于将lodash库导入文件。

## 例 1

### JavaScript

```
// Requiring the lodash library
const _ = require("lodash");

// The source object
var obj = { 'cpp': [{ 'java': { 'python': 3 } }] };

// Use of _.update() method
_.update(obj, 'cpp[0].java.python',
    function(n) { return n * n; });

// return the new object
console.log(obj.cpp[0].java.python);
```

**输出:**

```

```

## 例 2

### JavaScript

```
// Requiring the lodash library
const _ = require("lodash");

// The source object
var obj = { 'cpp': [{ 'java': { 'python': 3 } }] };

// Use of _.update() method
_.update(obj, 'html[0].css.javascript',
    function(n) { return n ? n + 1 : 0; });

// return the new object
console.log(obj.html[0].css.javascript);
```

**输出:**

```

```

**注意:** 这在正常的JavaScript中不会起作用，因为它需要安装库lodash。

**参考:** [https://lodash.com/docs/4.17.15#update](https://lodash.com/docs/4.17.15#update)