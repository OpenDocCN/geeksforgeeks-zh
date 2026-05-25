# Lodash _.reject() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-reject-method/](https://www.geeksforgeeks.org/lodash-_-reject-method/)

Lodash 是一个工作在下划线之上的 JavaScript 库。Lodash 有助于处理数组、集合、字符串、对象、数字等。
`_.reject()` 方法与 `_.filter()` 方法相反，此方法返回集合中谓词不返回 `true` 的元素。

## 语法

```
_.reject(collection, predicate)
```

## 参数

该方法接受两个参数，如上所述，如下所述:

*   `collection`: 此参数保存要迭代的集合。
*   `predicate`: 此参数保存每次迭代调用的函数。

## 返回值

此方法用于返回新过滤的数组。

## 示例 1

这里，`const _ = require('lodash')` 用于导入文件中的 lodash 库。

```javascript
// Requiring the lodash library 
const _ = require("lodash"); 

// Original array 
var users = [
  { 'user': 'Rohit', 'age': 25, 'active': false },
  { 'user': 'Mohit', 'age': 26, 'active': true } ];

// Use of _.reject() method

let gfg = _.reject(users, function(o) 
        { return !o.active; });

// Printing the output 
console.log(gfg);
```

**输出:**

```
[ { user: 'Mohit', age: 26, active: true } ]
```

## 示例 2

```javascript
// Requiring the lodash library 
const _ = require("lodash"); 

// Original array 
var users = [
  { 'employee': 'Rohit', 
    'salary': 50000, 
    'active': false 
  },
  { 'employee': 'Mohit', 
    'salary': 55000, 
    'active': true 
  } 
];

// Use of _.reject() method
// The `_.matches` iteratee shorthand
let gfg = _.reject(users, 
    { 'salary': 55000, 'active': true });

// Printing the output 
console.log(gfg);
```

**输出:**

```
[ { employee: Rohit, salary: 50000, active: false } ]
```

## 示例 3

```javascript
// Requiring the lodash library 
const _ = require("lodash"); 

// Original array 
var users = [
  { 'employee': 'Rohit', 
    'salary': 50000, 
    'active': false 
  },
  { 'employee': 'Mohit', 
    'salary': 55000, 
    'active': true 
  } 
];

// Use of _.reject() method
// The `_.matchesProperty` iteratee shorthand
let gfg = _.reject(users, ['active', false]);

// Printing the output 
console.log(gfg);
```

**输出:**

```
[ { employee: Mohit, salary: 55000, active: true } ]
```

## 示例 4

```javascript
// Requiring the lodash library 
const _ = require("lodash"); 

// Original array 
var users = [
  { 'employee': 'Rohit', 
    'salary': 50000, 
    'active': false 
  },
  { 'employee': 'Mohit', 
    'salary': 55000, 
    'active': true 
  } 
];

// Use of _.reject() method
// The `_.property` iteratee shorthand
let gfg = _.reject(users, 'active');

// Printing the output 
console.log(gfg);
```

**输出:**

```
[ { employee: Rohit, salary: 50000, active: false } ]
```

**注意:** 这段代码在正常的 JavaScript 中无法工作，因为它需要安装库 lodash。