# 下划线.js `_.camelCase()`方法

> 原文: [https://www.geeksforgeeks.org/underscore-js-_-camelcase-method/](https://www.geeksforgeeks.org/underscore-js-_-camelcase-method/)

`_.camelCase()`方法用于将破折号分隔的字符串转换为驼峰大小写字符串。

## 语法

```
_.camelCase( dashedString );
```

## 参数

*   `dashedString`: 此方法使用破折号来分隔字符串。

## 返回值

此方法返回转换后的`camelCase`字符串。

## 注意

这在正常的JavaScript中无法工作，因为它需要安装`underscore.js contrib`库。可以使用`npm install underscore-contrib`来安装`underscore.js contrib`库。

## 例1

### Javascript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var cml = _.camelCase( "a-ab-abc" );

console.log("The calmelCase String is : ", cml);
```

### 输出

```
The calmelCase String is :  aAbAbc
```

## 例2

### Javascript

```
// Defining underscore contrib variable
var _ = require('underscore-contrib');

var cml = _.camelCase( "geeks-for-geeks" );

console.log("The calmelCase String is : ", cml);
```

### 输出

```
The calmelCase String is :  geeksForGeeks
```