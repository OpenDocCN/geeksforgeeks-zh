# Date.addMonths() API

> 原文：[https://www.geeksforgeeks.org/node-js-date-addmonths-api/](https://www.geeksforgeeks.org/node-js-date-addmonths-api/)

`Date.addMonths()` 是一个用于操作 JS 日期和时间模块的极简函数集合，用于将额外的月份添加到现有的日期和时间。

## 所需模块

由 npm 安装模块或在本地使用。

*   使用 npm：

```js
npm install date-and-time --save
```

*   使用 CDN 链接：

```html
<script src="/path/to/date-and-time.min.js"></script>
```

## 语法

```js
addMonths(dateObj, months)
```

## 参数

该方法以下列参数为参数：

*   `dateobject`：是一个日期的字符串对象。
*   `months`：是要添加的月份数。

## 返回值

此方法返回更新后的日期和时间对象。

## 例 1

### index.js

```js
// Node.js program to demonstrate the
// Date.addMonths() method

// Importing module
const date = require('date-and-time')

// Creating object of current date and time
// by using Date()
const now = new Date();

// Adding Months to the existing date and time
// by using date.addMonths() method
const value = date.addMonths(now,24);

// Display the result
console.log("updated date and time : " + value)
```

使用以下命令运行 `index.js` 文件：

```bash
node index.js
```

### 输出

```text
updated date and time :
Thu Mar 09 2023 00:15:16 GMT+0530 (India Standard Time)
```

## 例 2

### index.js

```js
// Node.js program to demonstrate the
// Date.addMonths() method

// Importing module
const date = require('date-and-time')

// Creating object of current date and time
// by using Date()
const now = new Date();

now.setDate(20)

// Adding Months to the existing date and time
// by using date.addMonths() method
const value = date.addMonths(now,30);

// Display the result
console.log("updated date and time : " + value)
```

使用以下命令运行 `index.js` 文件：

```bash
node index.js
```

### 输出

```text
updated date and time :
Wed Sep 20 2023 00:16:10 GMT+0530 (India Standard Time)
```

## 参考

[https://github.com/knowledgecode/date-and-time#addmonthsdateobj-months](https://github.com/knowledgecode/date-and-time#addmonthsdateobj-months)