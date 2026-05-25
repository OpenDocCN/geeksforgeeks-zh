# Lodash `_.isPlainObject()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-isplainobject-method/](https://www.geeksforgeeks.org/lodash-_-isplainobject-method/)

Lodash 是一个工作在下划线之上的 JavaScript 库。Lodash 有助于处理数组、集合、字符串、lang、函数、对象、数字等。

## `_.isPlainObject()` 方法

`_.isPlainObject()` 方法检查值是一个普通对象，这意味着一个由对象构造函数创建的对象还是一个 `[[Prototype]]` 为空的对象。

### 语法

```javascript
_.isPlainObject(value)
```

### 参数

该方法接受如上所述的单个参数，描述如下：

*   `value`: 是用来校验值的函数。

### 返回值

如果值是普通对象，则该方法返回 `true`，否则返回 `false`。

### 示例 1

这里，`const _ = require('lodash')` 用于导入文件中的 lodash 库。

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Original array
var object = _.isPlainObject(Object.create(null));

// Using the _.isPlainObject() method
let plain_data = _.isPlainObject(object);

// Printing the output
console.log(plain_data);
```

**输出:**

```text
true
```

### 示例 2

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Original array
var object = _.isPlainObject([1, 2, 3]);

// Using the _.isPlainObject() method
let plain_data = _.isPlainObject(object);

// Printing the output
console.log(plain_data);
```

**输出:**

```text
false
```

### 示例 3

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Original array
var object = _.isPlainObject({ 'x': 0, 'y': 0 });

// Using the _.isPlainObject() method
let plain_data = _.isPlainObject(object);

// Printing the output
console.log(plain_data);
```

**输出:**

```text
true
```

**注意:** 这段代码在正常的 JavaScript 中无法工作，因为它需要安装库 lodash。