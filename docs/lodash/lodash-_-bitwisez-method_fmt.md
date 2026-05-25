# Lodash `_.bitwiseZ()`方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-bitwisez-method/](https://www.geeksforgeeks.org/lodash-_-bitwisez-method/)

`_.bitwiseZ()`方法返回对所有参数使用 `>>>` 运算符的结果。

## 语法

```javascript
_.bitwiseZ( val1, val2,..., valn );
```

## 参数

该方法取 `n` 个值对其进行 `>>>` 运算符位运算。

## 返回值

此方法返回对所有参数使用按位 `>>>` 运算符的结果。

## 注意

这在正常的 JavaScript 中不会起作用，因为它需要安装 `lodash-contrib` 库。可以使用 `npm install lodash-contrib --save`。

## 示例 1

```javascript
// Defining lodash contrib variable 
var _ = require('lodash-contrib'); 

var bZ  = _.bitwiseZ( 5 ); 

console.log("The bitwiseZ is :",bZ);
```

**输出:**

```
The bitwiseZ is : 5
```

## 示例 2

```javascript
// Defining lodash contrib variable 
var _ = require('lodash-contrib'); 

var bZ  = _.bitwiseZ( 1, 4, 6, 8 ); 

console.log("The bitwiseZ is :",bZ);
```

**输出:**

```
The bitwiseZ is : 0
```

## 示例 3

```javascript
// Defining lodash contrib variable 
var _ = require('lodash-contrib'); 

var bZ  = _.bitwiseZ( 72, 36 ); 

console.log("The bitwiseZ is :",bZ);
```

**输出:**

```
The bitwiseZ is : 4
```

## 示例 4

```javascript
// Defining lodash contrib variable 
var _ = require('lodash-contrib'); 

var bZ  = _.bitwiseZ( 72, 36, 2 ); 

console.log("The bitwiseZ is :",bZ);
```

**输出:**

```
The bitwiseZ is : 1
```