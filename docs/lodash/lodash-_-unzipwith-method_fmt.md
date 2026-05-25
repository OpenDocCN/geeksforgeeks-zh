# Lodash _.unzipWith()方法

> 原文：[https://www.geeksforgeeks.org/lodash-_-unzipwith-method/](https://www.geeksforgeeks.org/lodash-_-unzipwith-method/)

`_.unzipWith()`方法接受一个迭代函数来指定应该如何组合重新分组的值。该迭代函数会用每个分组的对应元素进行调用。

## 语法

```
_.unzipWith(array, [iteratee = _.identity])
```

## 参数

该方法接受两个参数，如下所述：

*   `array`：此参数存储待处理的分组元素数组。
*   `[iteratee = _.identity]`：此参数是用于组合重组值的函数。

## 返回值

此方法返回包含重组元素的新数组。

## 示例 1

这里，`const _ = require('lodash')`用于将lodash库导入文件。

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Original array
var zipped_arr = _.zip([15, 7], [185, 20], [478, 123]);

// Use of _.unzipWith() method
let gfg = _.unzipWith(zipped_arr, _.subtract);

// Printing the output
console.log(gfg)
```

**输出：**

```
[8, 165, 355]
```

## 示例 2

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Original array
var zipped_arr = _.zip([4, 9], [185, 20], [478, 123]);

// Use of _.unzipWith() method
let gfg = _.unzipWith(zipped_arr, _.add);

// Printing the output
console.log(gfg)
```

**输出：**

```
[13, 205, 601]
```