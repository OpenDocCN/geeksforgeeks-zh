# Lodash _.dec()方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-dec-method/](https://www.geeksforgeeks.org/lodash-_-dec-method/)

`Lodash _.dec()`方法通过给定值减 1 返回结果。

## 语法

```
_.dec( value );
```

## 参数

该方法取值并递减。

## 返回值

该方法通过给定值减 1 返回结果。

## 注意

这在正常的 JavaScript 中不会起作用，因为它需要安装 `lodash.js contrib` 库。可以使用 `npm install lodash-contrib --save` 安装 Lodash.js contrib 库。

## 例 1

### Javascript

```
// Defining lodash contrib variable 
var _ = require('lodash-contrib');

var val = 33 
var decrVal  = _.dec( val );

console.log("The Given value is :", val); 
console.log("The Decrement of Given value is :", decrVal);
```

### 输出

```
The Given value is : 33
The Decrement of Given value is : 32
```

## 例二

### Javascript

```
// Defining lodash contrib variable 
var _ = require('lodash-contrib');

var val = 100 
var decrVal  = _.dec( val );

console.log("The Given value is :", val); 
console.log("The Decrement of Given value is :", decrVal);
```

### 输出

```
The Given value is : 100
The Decrement of Given value is : 99
```