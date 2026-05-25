# 洛达什 `_.isArrayLikeObject()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-isarraylikeobject-method/](https://www.geeksforgeeks.org/lodash-_-isarraylikeobject-method/)

洛达什 `_.isArrayLikeObject()` 方法检查给定值是否是类似数组的对象。 这个方法类似于 `_.isArrayLike()` 方法，除了它还检查值是否是一个对象。

**语法:**

`_.isArrayLikeObject( value )`

**参数:** 该方法接受如上所述的单个参数，如下所述:

*   `value`: 此参数保存要检查是否为数组对象的值。

**返回值:** 该方法返回一个布尔值。

## 示例 1

该方法为数组返回 `true`，因为它也是一个对象。

### Javascript

```javascript
// Defining Lodash variable
const _ = require('lodash');

var val = [1, 2, 3];

// Checking for an ArrayLikeObject
console.log("The Value is ArrayLikeObject : " 
    +_.isArrayLikeObject(val));
```

**输出:**

```
The Value is ArrayLikeObject : true
```

## 例 2

该方法返回 `false` 为字符串，因为它不是一个对象。

### Javascript

```javascript
// Defining Lodash variable
const _ = require('lodash');

var val = "GeeksforGeeks";

// Checking for an ArrayLikeObject
console.log("The Value is ArrayLikeObject : " 
    +_.isArrayLikeObject(val)); 
```

**输出:**

```
The Value is ArrayLikeObject : false
```

## 例三

### Javascript

```javascript
// Defining Lodash variable
const _ = require('lodash');

var val = { 1:1 };

// Checking for an ArrayLikeObject
console.log("The Value is ArrayLikeObject : " 
    +_.isArrayLikeObject(val)); 
```

**输出:**

```
The Value is ArrayLikeObject : false
```

**注意:** 这在正常的 JavaScript 中无法工作，因为它需要安装 lodash 库，并且可以使用 `npm install lodash` 进行安装。