# Lodash _.mergeWith() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-mergewith-method/](https://www.geeksforgeeks.org/lodash-_-mergewith-method/)

Lodash 是一个工作在 Underscore.js 之上的 JavaScript 库，有助于处理数组、字符串、对象、数字等。

`_.mergeWith()` 方法使用一个定制函数，调用该函数来产生给定目标和源属性的合并值。当定制函数返回 `undefined` 时，合并由方法处理。这几乎与 `_.merge()` 方法相同。

## 语法

```
_.mergeWith( object, sources, customizer )
```

## 参数

该方法接受三个参数，如下所述：

*   `object`: 此参数保存目标对象。
*   `sources`: 此参数保存来源对象。这是一个可选参数。
*   `customizer`: 这是定制赋值的功能。

## 返回值

该方法返回 `object`。

## 示例 1

```javascript
// Requiring the lodash library
const _ = require("lodash");

// The destination object
var object = {
  'amit': [{ 'susanta': 20 }, { 'durgam': 40 }]
};

// The source object
var other = {
  'amit': [{ 'chinmoy': 30 }, { 'kripamoy': 50 }]
};

// Using the _.mergeWith() method
console.log(_.mergeWith(object, other));
```

**输出:**

> { amit: [ { chinmoy: 30, susanta: 20 }, { kripamoy: 50, durgam: 40 } ] }

## 示例 2

```javascript
// Requiring the lodash library
const _ = require("lodash");

// Defining the customizer function
function customizer(obj, src) {
  if (_.isArray(obj)) {
    return obj.concat(src);
  }
}

// The destination object
var object = {
  'amit': [{ 'susanta': 20 }, { 'durgam': 40 }]
};

// The source object
var other = {
  'amit': [{ 'chinmoy': 30 }, { 'kripamoy': 50 }]
};

// Using the _.mergeWith() method
console.log(_.mergeWith(object, other, customizer));
```

**输出:**

> { amit: [ { susanta: 20, chinmoy: 30 }, { durgam: 40, kripamoy: 50 } ] }