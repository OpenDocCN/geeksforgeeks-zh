# _.conformsTo()方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-conformto-method/](https://www.geeksforgeeks.org/lodash-_-conformto-method/)

Lodash 是一个工作在下划线之上的 JavaScript 库。Lodash 有助于处理数组、集合、字符串、对象、数字等。

`_.conformsTo()`方法用对象的对应属性值调用`source`的谓词属性，检查对象是否符合`source`，这个方法等价于`_.conforms`的部分应用。

## 语法

```
_.conformsTo(object, source)
```

## 参数

该方法接受两个参数，如下所述：

*   `object`: 是方法要考察的对象。
*   `source`: 是属性谓词要符合的对象。

## 返回值

这个方法返回一个布尔值，表示对象的属性是否符合`source`中的谓词。

## 示例 1

这里，`const _ = require('lodash')`用于导入文件中的 lodash 库。

```
// Requiring the lodash library
const _ = require("lodash");

// Original array
var object = { 'p': 11, 'q': 9 };

// Using the _.conformsTo() method
let conform_data = _.conformsTo(object, {
    'q': function(n) { return n > 1; }
});

// Printing the output
console.log(conform_data);
```

**输出:**

```
true
```

## 示例 2

```
// Requiring the lodash library
const _ = require("lodash");

// Original array
var object = { 'x': 1, 'y': 3 };

// Using the _.conformsTo() method
let conform_data = _.conformsTo(object, {
    'q': function(n) { return n > 3; }
});

// Printing the output
console.log(conform_data);
```

**输出:**

```
false
```

**注意:** 这段代码在正常的 JavaScript 中无法工作，因为它需要安装库 lodash。