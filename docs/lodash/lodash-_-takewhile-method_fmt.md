# `_.takeWhile()`方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-takewhile-method/](https://www.geeksforgeeks.org/lodash-_-takewhile-method/)

`_.takeWhile()`方法用于创建一个数组切片，其中的元素是从开始处获取的。此外，这些元素一直被获取，直到谓词函数首次返回`false`。

## 语法

```
_.takeWhile(array, [predicate=_.identity])
```

## 参数

该方法接受两个参数：

*   `array`: 此参数存储要查询的数组。
*   `[predicate=_.identity]`: 此参数持有在每次迭代中调用的函数。

## 返回值

此方法用于返回数组的切片。

## 示例 1

这里，`const _ = require('lodash')`用于导入文件中的lodash库。

```javascript
// Requiring the lodash library 
const _ = require("lodash"); 

// Original array 
var users = [
  { 'user': 'jupiter',  'active': false },
  { 'user': 'mercury',    'active': false },
  { 'user': 'saturn', 'active': true }
];

// Use of _.takeWhile() 
// method
let gfg = _.takeWhile(users, function(o) { return !o.active; });

// Printing the output 
console.log(gfg);
```

**输出:**

```
[{ user: 'jupiter', active: false },
 {user: 'mercury', active: false}]
```

## 示例 2

```javascript
// Requiring the lodash library 
const _ = require("lodash"); 

// Original array 
var users = [
  { 'user': 'jupiter',  'active': false },
  { 'user': 'mercury',    'active': false },
  { 'user': 'saturn', 'active': true }
];

// Use of _.takeWhile() 
// method
// The `_.matches` iteratee shorthand.

let gfg = _.takeWhile(users, { 'user': 'jupiter', 'active': false });

// Printing the output 
console.log(gfg);
```

**输出:**

```
[{ user: 'jupiter', active: false }]
```

## 示例 3

```javascript
// Requiring the lodash library 
const _ = require("lodash"); 

// Original array 
var users = [
  { 'user': 'jupiter',  'active': false },
  { 'user': 'mercury',    'active': false },
  { 'user': 'saturn', 'active': true }
];

// Use of _.takeWhile() 
// method
// The `_.matchesProperty` iteratee shorthand.

let gfg = _.takeWhile(users, ['active', false]);

// Printing the output 
console.log(gfg);
```

**输出:**

```
[{ user: 'jupiter', active: false },
 {user: 'mercury', active: false}]
```

## 示例 4

```javascript
// Requiring the lodash library 
const _ = require("lodash"); 

// Original array 
var users = [
  { 'user': 'jupiter',  'active': false },
  { 'user': 'mercury',    'active': false },
  { 'user': 'saturn', 'active': true }
];

// Use of _.takeWhile() 
// method
// The `_.property` iteratee shorthand.

let gfg = _.takeWhile(users, 'active');

// Printing the output 
console.log(gfg);
```

**输出:**

```
[]
```

**注意:** 这段代码在正常的JavaScript中无法工作，因为它需要安装库lodash。