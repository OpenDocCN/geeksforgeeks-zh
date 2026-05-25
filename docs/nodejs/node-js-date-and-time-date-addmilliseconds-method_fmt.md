# Node.js 日期时间 `date.addMilliseconds()` 方法

> 原文：[https://www.geeksforgeeks.org/node-js-date-and-time-date-addmilliseconds-method/](https://www.geeksforgeeks.org/node-js-date-and-time-date-addmilliseconds-method/)

`date.addMilliseconds()` 方法用于将额外的毫秒添加到现有的日期和时间。

## 所需模块

通过 `npm` 安装模块或在本地使用。

*   **使用 NPM：**

```js
npm install date-and-time --save
```

*   **使用 CDN 链接：**

```js
<script src="/path/to/date-and-time.min.js"></script>
```

## 语法

```js
const addMilliseconds(dateObj, seconds)
```

## 参数

该方法接受以下参数：

*   `dateobject`：一个日期的字符串对象。
*   `seconds`：要添加的毫秒数。

## 返回值

此方法返回更新后的日期和时间。

## 示例 1

### index.js

```js
// Node.js program to demonstrate the
// Date.addMilliseconds() method

// Importing date-and-time module
const date = require('date-and-time')

// Creating object of current date
// and time using Date() method
const now = new Date();

// Adding Milliseconds to the existing date and time
// by using date.addMilliseconds() method
const value = date.addMilliseconds(now,24);

// Display the result
console.log("updated date and time :- " + value)
```

使用以下命令运行 `index.js` 文件：

```js
node index.js
```

**输出：**

```js
updated date and time :- Fri Mar 19 2021 18:15:26 GMT+0530 (India Standard Time)
```

## 示例 2

### index.js

```js
// Node.js program to demonstrate the
// Date.addMilliseconds() method

// Importing date-and-time module
const date = require('date-and-time')

// Creating object of current date
// and time using Date() method
const now = new Date();

now.setDate(20)

// Adding Milliseconds to the existing
// date and time by using
// date.addMilliseconds() method
const value = date.addMilliseconds(now,30);

// Display the result
console.log("updated date and time :- " + value)
```

使用以下命令运行 `index.js` 文件：

```js
node index.js
```

**输出：**

```js
updated date and time :- Sat Mar 20 2021 18:16:05 GMT+0530 (India Standard Time)
```

**参考：** [https://github.com/nickelcase/date-and-time](https://github.com/nickelcase/date-and-time)