# `_.runInContext()` 方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-runincontext-method/](https://www.geeksforgeeks.org/lodash-_-runincontext-method/)

**Lodash** 是一个工作在下划线.js之上的 JavaScript 库，Lodash 有助于处理数组、字符串、对象、数字等。

`_.runInContext()` 方法用于使用给定的上下文对象创建一个新的 lodash 函数。

## 语法

```
_.runInContext( context )
```

## 参数

该方法接受如上所述的单个参数，如下所述:

*   `context`: 保存创建新函数的上下文对象。

## 返回值

这个方法返回一个新的 lodash 函数。

## 示例 1

### JavaScript

```
// Requiring the lodash library 
const _ = require("lodash"); 

// Creating an object variable
_.mixin({ 'foo': _.constant('foo') });

var func = _.runInContext();
func.mixin({ 'bar': func.constant('bar') });    

// Using the value() method
let val = _.isFunction(_.foo);

// Display the output 
console.log(val);
```

**输出:**

```
true
```

## 示例 2

### JavaScript

```
// Requiring the lodash library 
const _ = require("lodash"); 

// Creating an object variable
_.mixin({ 'foo': _.constant('foo') });

var func = _.runInContext();
func.mixin({ 'bar': func.constant('bar') });    

// Using the value() method
let val = _.isFunction(_.bar);

// Display the output 
console.log(val);
```

**输出:**

```
false
```

## 示例 3

### JavaScript

```
// Requiring the lodash library 
const _ = require("lodash"); 

// Creating an object variable
_.mixin({ 'foo': _.constant('foo') });

var func = _.runInContext();
func.mixin({ 'bar': func.constant('bar') });    

// Using the value() method
let val = func.isFunction(func.foo);

// Display the output 
console.log(val);
```

**输出:**

```
false
```

## 示例 4

### JavaScript

```
// Requiring the lodash library 
const _ = require("lodash"); 

// Creating an object variable
_.mixin({ 'foo': _.constant('foo') });

var func = _.runInContext();
func.mixin({ 'bar': func.constant('bar') });    

// Using the value() method
let val = func.isFunction(func.bar);

// Display the output 
console.log(val);
```

**输出:**

```
true
```