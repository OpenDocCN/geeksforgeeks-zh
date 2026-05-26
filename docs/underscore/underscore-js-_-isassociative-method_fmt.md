# 下划线.js `_.isAssociative()`方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-isassociative-method/](https://www.geeksforgeeks.org/underscore-js-_-isassociative-method/)

`_.isAssociative()`方法检查给定值是否关联。关联对象是指可以通过键或索引访问其元素的对象，例如数组。

**语法:**
```javascript
_.isAssociative(value);
```

**参数:** 该方法接受如上所述的单个参数，如下所述:
* `value`: 要检查关联的给定值。

**返回值:** 该方法返回一个`Boolean`值（如果给定值是关联的，则返回`true`，否则返回`false`）。

**注意:** 这在正常的 JavaScript 中无法工作，因为它需要安装`underscore-contrib`库。

`underscore-contrib`库可以使用以下命令安装：
```bash
npm install underscore-contrib
```

## 示例 1: 为数组返回 true 的方法。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 
// Checking
console.log("The Value is Associative : " +_.isAssociative([1,2,3,4])); 
```

**输出:**
```
The Value is Associative : true
```

## 示例 2: 为整数返回 false 的方法。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 
// Checking
console.log("The Value is Associative : " +_.isAssociative(2));
```

**输出:**
```
The Value is Associative : false
```

## 示例 3: 对于映射，此方法返回 true，因为其值可由键访问。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 
// Checking
console.log("The Value is Associative : " +_.isAssociative({1:2, 3:3}));
```

**输出:**
```
The Value is Associative : true
```

## 示例 4: 为字符串变量返回 false 的方法。

```javascript
// Defining underscore contrib variable
var _ = require('underscore-contrib'); 
// Checking
console.log("The Value is Associative : " +_.isAssociative("GeeksforGeeks"));
```

**输出:**
```
The Value is Associative : false
```