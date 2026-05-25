# `_.isValidDate()`方法

> 原文：[https://www.geeksforgeeks.org/lodash-_-isvaliddate-method/](https://www.geeksforgeeks.org/lodash-_-isvaliddate-method/)

`Lodash`是一个工作在`underscore.js`之上的JavaScript库，有助于处理数组、字符串、对象、数字等。

`_.isValidDate()`方法用于检查给定值是否为有效日期。它检查该值是否是`Date`对象的实例，并且该`Date`对象是否代表一个有效日期。

**注意：**此方法不验证原始输入字符串是否对应一个真实存在的日历日期。例如，日期字符串“02/30/2014”会被视为有效，因为`Date`对象将其解释为“03/02/2014”，这是一个有效的日期。像`Moment.js`这样的库可以用来验证表示日期的字符串。

**语法：**

```javascript
_.isValidDate( value )
```

**参数：**该方法接受如上所述的单个参数，如下所述：

*   `value`：此参数保存需要检查其是否为有效日期的值。

**返回值：**这个方法返回一个布尔值。如果给定值是有效日期，则返回`true`，否则返回`false`。

**注意：**这在普通的JavaScript环境中不会起作用，因为它需要安装`lodash-contrib`库。可以使用以下命令来安装：
```bash
npm install lodash-contrib --save
```

**例1：**

## JavaScript

```javascript
// Defining Lodash variable 
const _ = require('lodash-contrib');

var validDate = new Date("10/02/2014");
var invalidDate = new Date("10/32/2014");

// Checking for Valid Date Object 
console.log("The Value of Valid Date : " +
  _.isValidDate(validDate));
console.log("The Value of Invalid Date : " +
  _.isValidDate(invalidDate));
```

**输出：**

```
The Value of Valid Date : true
The Value of Invalid Date : false
```

**例2：**

## JavaScript

```javascript
// Defining Lodash-contrib variable 
const _ = require('lodash-contrib');

var val = "World War 2";

// Checking for Valid Date Object 
console.log("The Value of Date : " +
  _.isValidDate(val));
```

**输出：**

```
The Value of Date : false
```