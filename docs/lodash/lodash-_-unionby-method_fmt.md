# Lodash `_.unionBy()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-unionby-method/](https://www.geeksforgeeks.org/lodash-_-unionby-method/)

`_.unionBy()` 方法接受一个迭代函数，该函数会为每个数组的每个元素调用，以生成计算唯一性的标准。结果值的顺序由值出现的第一个数组决定。

## 语法

```javascript
_.unionBy(array, [iteratee = _.identity])
```

## 参数

该方法接受两个参数，如下所述：

*   `array`: 此参数保存要检查的数组。
*   `[iteratee = _.identity]`: 此参数保存为每个元素调用的迭代函数。

## 返回值

此方法用于返回新的组合值数组。

## 示例 1

这里，`const _ = require('lodash')` 用于将 lodash 库导入文件。

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.unionBy() method
let gfg = _.unionBy([{ 'y': 1 }],
                    [{ 'y': 2 }, { 'y': 1 }],
                    [{ 'y': 3 }], 'y');

// Printing the output
console.log(gfg)
```

**输出:**

```javascript
[ { 'y': 1 }, { 'y': 2 }, {'y': 3} ]
```

## 示例 2

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Use of _.unionBy() method
let gfg = _.unionBy([1.5],
                    [2.6, 2.7],
                    [2.3, 3.8], Math.floor);

// Printing the output
console.log(gfg)
```

**输出:**

```javascript
[1.5, 2.6, 3.8]
```