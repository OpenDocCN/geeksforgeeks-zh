# 洛达什 `_.sortedLastIndexBy()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-sortedlastindexby-method/](https://www.geeksforgeeks.org/lodash-_-sortedlastindexby-method/)

`_.sortedLastIndexBy()` 方法用于返回数组中可以插入元素的最高索引，并保持其排序顺序。此外，它接受对值和数组的每个元素调用的迭代来计算它们的排序。

## 语法

```
_.sortedLastIndexBy(array, value, [iteratee=_.identity])
```

## 参数

该方法接受三个参数，如上所述，如下所述:

*   `array`: 此参数存储已排序的数组。
*   `value`: 此参数存储要评估的值。
*   `iteratee`: 这是一个迭代每个元素的函数。

## 返回值

该方法返回值应该插入数组的索引。

## 示例 1

这里，`const _ = require('lodash')` 用于将 lodash 库导入文件。

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Original array
var objects = [{ 'x': 4 }, { 'x': 6 }];

// Use of _.sortedLastIndexBy()
// method
let index = _.sortedLastIndexBy(objects,
    { 'x': 5 }, function(o) { return o.x; });

// Printing the output
console.log(index);
```

**输出:**

```
1
```

## 示例 2

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Original array
var objects = [{ 'x': 4 }, { 'x': 6 }];

// Use of _.sortedLastIndexBy()
// method
let index = _.sortedLastIndexBy(
        objects, { 'x': 9 }, 'x');

// Printing the output
console.log(index);
```

**输出:**

```
2
```

## 示例 3

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Original array
let x = ['ajax', 'django', 'mongoDb',
       'react', 'reactnative', 'yarn']

// Use of _.sortedIndexBy()
// method
let index = _.sortedIndexBy(x, 'luby', 5);

// Printing the output
console.log(index);
```

**输出:**

```
3
```

**注意:** 这在正常的 JavaScript 中不会起作用，因为它需要安装库 lodash。