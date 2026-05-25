# Node.js Date.addHours() API

> 哎哎哎:# t0]https://www.geeksforgeeks.org/node-js-date-add-hours-API/

`Date.addHours()` 是操作 JS 日期和时间模块的极简函数集合，用于将额外的小时数添加到现有的日期和时间。

## 所需模块

由 npm 安装模块或在本地使用。

*   通过 npm 安装。

```bash
npm install date-and-time --save
```

*   使用 CDN 链接。

```html
<script src="/path/to/date-and-time.min.js"></script>
```

## 语法

```javascript
addHours(dateObj, hours)
```

## 参数

该方法以下列参数为参数:

*   `dateobject`: 是一个日期的字符串对象。
*   `Hours`: 是小时数。

## 返回值

此方法返回更新的日期和时间。

## 示例 1

### index.js

```javascript
// Node.js program to demonstrate the
// Date.addHours() method

// Importing module
const date = require('date-and-time')

// Creating object of current date and time
// by using Date()
const now = new Date();

// Adding Hours to the existing date and time
// by using date.addHours() method
const value = date.addHours(now, 24);

// Display the result
console.log("updated date and time : " + value)
```

使用以下命令运行 `index.js` 文件:

```bash
node index.js
```

输出:

```text
updated date and time :
Mon Mar 08 2021 20:35:37 GMT+0530 (India Standard Time)
```

## 示例 2

### index.js

```javascript
// Node.js program to demonstrate the
// Date.addHours() method

// Importing module
const date = require('date-and-time')

// Creating object of current date and time
// by using Date()
const now = new Date();

now.setDate(20)

// Adding Hours to the existing date and time
// by using date.addHours() method
const value = date.addHours(now, 30);

// Display the result
console.log("updated date and time : " + value)
```

使用以下命令运行 `index.js` 文件:

```bash
node index.js
```

输出:

```text
updated date and time :
Mon Mar 22 2021 02:37:29 GMT+0530 (India Standard Time)
```

参考: T2