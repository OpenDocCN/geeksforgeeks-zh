# 洛达什 `_.exists()` 方法

> 原文：`https://www.geeksforgeeks.org/lodash-_-exists-method/`

`_.exists()` 方法检查给定值是否为“存在”（Exist），并返回相应的布尔值。`null` 和 `undefined` 都被认为是不存在的值。所有其他值都是“存在”（Existy）。

## 语法

```javascript
_.exists( value );
```

## 参数

该方法接受如上所述的单个参数，描述如下：

*   `value`：要检查其存在性的给定值。

## 返回值

如果给定值为“存在”（Existy），则该方法返回布尔值 `true`，否则返回 `false`。

## 注意

这在正常的 JavaScript 中无法工作，因为它需要安装 `lodash-contrib` 库。可以使用 `npm install lodash-contrib` 来安装。

## 例 1

```javascript
// Defining underscore lodash variable 
var _ = require('lodash-contrib'); 

var bool = _.exists("Geeks");

console.log("Check the Existenc of Given Value : ", bool);
```

**输出：**

```
Check the Existenc of Given Value : true
```

## 例 2

```javascript
// Defining underscore lodash variable 
var _ = require('lodash-contrib'); 

var bool = _.exists(undefined); 

console.log("Check the Existenc of Given Value : ", bool);
```

**输出：**

```
Check the Existenc of Given Value : false
```

## 例 3

```javascript
// Defining underscore lodash variable 
var _ = require('lodash-contrib'); 

var bool = _.exists(null);

console.log("Check the Existenc of Given Value : ", bool);
```

**输出：**

```
Check the Existenc of Given Value : false
```

## 例 4

```javascript
// Defining underscore lodash variable 
var _ = require('lodash-contrib'); 

var bool = _.exists([1, 12, 2, 3]);

console.log("Check the Existenc of Given Value : ", bool);
```

**输出：**

```
Check the Existenc of Given Value : true
```