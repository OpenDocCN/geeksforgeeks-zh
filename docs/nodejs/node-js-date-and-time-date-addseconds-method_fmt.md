# Node.js 日期时间 `Date.addSeconds()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-date-and-time-date-addseconds-method/](https://www.geeksforgeeks.org/node-js-date-and-time-date-addseconds-method/)

`Date.addSeconds()` 方法用于将额外的秒添加到现有的日期和时间。

## 所需模块

由 npm 安装模块或在本地使用。

*   **通过 NPM 安装:**

```js
npm install date-and-time --save
```

*   **通过 CDN 链接:**

```js
<script src="/path/to/date-and-time.min.js"></script>
```

## 语法

```js
const addSeconds(dateObj, seconds)
```

## 参数

该方法以下列参数为参数:

*   `dateobject`: 是一个日期的字符串对象。
*   `seconds`: 是要添加的秒数。

## 返回值

此方法返回更新的日期和时间。

## 示例 1

### index.js

```js
// Node.js program to demonstrate the
// Date.addSeconds() method

// Importing date-and-time module
const date = require('date-and-time')

// Creating object of current date and time
// by using Date()
const now = new Date();

// Adding Seconds to the existing date and time
// by using date.addSeconds() method
const value = date.addSeconds(now,24);

// Display the result
console.log("updated date and time :- " + value)
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

> updated date and time :- Fri Mar 19 2021 18:13:08 GMT+0530 (India Standard Time)

## 示例 2

### index.js

```js
// Node.js program to demonstrate the
// Date.addSeconds() method

// Importing date-and-time module
const date = require('date-and-time')

// Creating object of current date and time
// by using Date()
const now = new Date();

now.setDate(20)

// Adding Seconds to the existing date and time
// by using date.addSeconds() method
const value = date.addSeconds(now,30);

// Display the result
console.log("updated date and time :- " + value)
```

使用以下命令运行 `index.js` 文件:

```js
node index.js
```

**输出:**

> updated date and time :- Sat Mar 20 2021 18:04:43 GMT+0530 (India Standard Time)

## 参考

[https://github.com/knowledgecode/date-and-time#addsecondsdateobj-seconds](https://github.com/knowledgecode/date-and-time#addsecondsdateobj-seconds)