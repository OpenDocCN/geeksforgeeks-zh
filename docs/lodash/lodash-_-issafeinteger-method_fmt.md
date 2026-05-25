# Lodash _.isSafeInteger()方法

> 原文: [https://www.geeksforgeeks.org/lodash-_-issafeinteger-method/](https://www.geeksforgeeks.org/lodash-_-issafeinteger-method/)

**Lodash** 是一个工作在下划线.js之上的JavaScript库，Lodash有助于处理数组、字符串、对象、数字等。

`_.isSafeInteger()`方法用于查找给定值是否为安全整数。如果给定值是安全整数，则返回真。否则，它返回`false`。如果整数是IEEE-754双精度数（从(2<sup>53</sup>–1)到-(2<sup>53</sup>–1)的所有整数），并且不是舍入的不安全整数的结果，则该整数是安全的。

## 语法

```
_.isSafeInteger(value)
```

## 参数

该方法接受如上所述的单个参数，如下所述：

*   `value`: 该参数保存要检查的值。

## 返回值

如果该值是安全整数，则该方法返回`true`，否则返回`false`。

## 注意

这里，`const _ = require('lodash')`用于将lodash库导入文件。

## 例 1

```
// Requiring the lodash library
const _ = require("lodash");

// Use of _.isSafeInteger() method

// Passing a mathematical pow function as an argument
console.log(_.isSafeInteger(Math.pow(2, 53) - 1));

// Passing a maximum value of a number as an argument
console.log(_.isSafeInteger(Infinity));

// Passing a minimum value of a number as an argument
console.log(_.isSafeInteger(Number.MIN_VALUE));
```

**输出:**

```
true
false
false
```

## 例 2

```
// Requiring the lodash library
const _ = require("lodash");

// Use of _.isSafeInteger() method

// Passing a positive number as an argument
console.log(_.isSafeInteger(123));

// Passing a negative number as an argument
console.log(_.isSafeInteger(-123));

// Passing a number(with decimals) as an argument
console.log(_.isSafeInteger(0.123));
```

**输出:**

```
true
true
false
```

## 注意

这段代码在正常的JavaScript中无法工作，因为它需要安装库lodash。

## 参考资料

[https://lodash.com/docs/4.17.15#isSafeInteger](https://lodash.com/docs/4.17.15#isSafeInteger)