# Lodash _.isMap() 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-ismap-method/](https://www.geeksforgeeks.org/lodash-_-ismap-method/)

Lodash `_.isMap()` 方法检查给定值是否为 Map 对象，并返回相应的布尔值。

## 语法

```
_.isMap( value )
```

## 参数

该方法接受如上所述的单个参数，描述如下：

*   `value`: 该参数保存需要检查的值是否为 Map 对象。

## 返回值

该方法返回一个布尔值（如果给定值是 Map 对象，则返回 `true`，否则返回 `false`）。

## 示例 1

### JavaScript

```
// Defining Lodash variable
const _ = require('lodash');

var testMap = new Map;

// Checking for Map
console.log("The Value is Map : "
        + _.isMap(testMap));
```

**输出:**

```
The Value is Map : true
```

## 示例 2

对于 WeakMap 对象，此方法返回 `false`。

### JavaScript

```
// Defining Lodash variable
const _ = require('lodash');

var testMap = new WeakMap;

// Checking for Map
console.log("The Value is Map : "
        + _.isMap(testMap));
```

**输出:**

```
The Value is Map : false
```

## 示例 3

对于字符串，返回 `false`。

### JavaScript

```
// Defining Lodash variable
const _ = require('lodash');

// Checking for Map
console.log("The Value is Map : "
        + _.isMap("map"));
```

**输出:**

```
The Value is Map : false
```