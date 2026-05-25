# `_.toPairsIn()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-topairsin-method/](https://www.geeksforgeeks.org/lodash-_-topairsin-method/)

`_.toPairsIn()` 方法用于为对象创建一个自己的和继承的可枚举字符串键值对的数组，该数组可由 `_.pairs` 函数转换。如果对象是 `Map` 或 `Set`，则返回其条目。

**语法:**

```javascript
_.toPairsIn(object)
```

**参数:** 该方法接受如上所述的单个参数，如下所述:

*   `object`: 此参数保存要查询的对象。

**返回值:** 这个方法返回键值对的数组。

### 示例 1

```javascript
// Requiring the lodash library
const _ = require("lodash");

function Fb() {
  this.id = 2045;
  this.username = 'fb_myself';
  this.password = 'fb1234';
}

Fb.prototype.email = 'myself@gmail.com';

// Use of _.toPairsIn() method
console.log(_.toPairsIn(new Fb));
```

**输出:**

```javascript
[
  [ 'id', 2045 ],
  [ 'username', 'fb_myself' ],
  [ 'password', 'fb1234' ],
  [ 'email', 'myself@gmail.com' ]
]
```

### 示例 2

```javascript
// Requiring the lodash library
const _ = require("lodash");

function Gfg() {
  this.x = 1;
  this.y = 2;
}

Gfg.prototype.z = 3;

// Use of _.toPairsIn() method
console.log(_.toPairsIn(new Gfg));
```

**输出:**

```javascript
[ ['x', 1], ['y', 2], ['z', 3] ]
```

### 示例 3

```javascript
// Requiring the lodash library
const _ = require("lodash");

var GfG = {
    "Geek": "GFG"
}

// Use of _.toPairsIn() method
console.log(_.toPairsIn(GfG));
```

**输出:**

```javascript
[ [ 'Geek', 'GFG' ] ]
```