# 洛达什 `_.isArrayLike()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-isarraylike-method/](https://www.geeksforgeeks.org/lodash-_-isarraylike-method/)

洛达什 `_.isArrayLike()` 方法检查该值是否像数组一样。如果一个值不是一个函数并且有一个 `length` 属性，那么它就被认为是类似数组的。`length` 是大于或等于 0 且小于或等于 `Number.MAX_SAFE_INTEGER` 的整数。

## 语法

```
_.isArrayLike(value)
```

## 参数

该方法接受如上所述的单个参数，如下所述：

*   `value`: 此参数存储需要检查的类似数组的值。

## 返回值

该方法返回一个布尔值。

## 示例

### 例 1

此方法对数组返回 `true`。

```javascript
// Defining Lodash variable
const _ = require('lodash');

var val = [1, 2, 3]

// Checking for an ArrayLike
console.log("The Value is ArrayLike : "
    +_.isArrayLike(val));
```

**输出:**

```
The Value is ArrayLike : true
```

### 示例 2

该方法对字符串返回 `true`，因为可以计算它们的长度。

```javascript
// Defining Lodash variable
const _ = require('lodash');

var val = "GeeksforGeeks";
// Checking for an ArrayLike
console.log("The Value is ArrayLike : "
    +_.isArrayLike(val));
```

**输出:**

```
The Value is ArrayLike : true
```

### 例 3

当此方法返回 `false` 时。

```javascript
// Defining Lodash variable
const _ = require('lodash');

var val = { 1:1 };
// Checking for an ArrayLike
console.log("The Value is ArrayLike : "
    +_.isArrayLike(val));
```

**输出:**

```
The Value is ArrayLike : false
```

**注意:** 这在正常的 JavaScript 中不会起作用，因为它需要安装 lodash 库，可以使用 `npm install lodash` 进行安装。