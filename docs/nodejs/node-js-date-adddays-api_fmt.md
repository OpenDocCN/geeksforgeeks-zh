# Node.js Date.addDays() API

> 原文：[https://www.geeksforgeeks.org/node-js-date-adddays-api/](https://www.geeksforgeeks.org/node-js-date-adddays-api/)

`Date.addDays()` 是操作 JS 日期和时间模块的极简函数集合，用于将额外的天数添加到现有的日期和时间。

**所需模块：** 由 npm 安装模块或在本地使用。

*   通过 npm 安装。

```bash
npm install date-and-time --save
```

*   使用 CDN 链接。

```html
<script src="/path/to/date-and-time.min.js"></script>
```

**语法：**

```javascript
addDays(dateObj, days)
```

**参数：** 该方法以下列参数为参数：

*   `dateobject`：是一个日期的字符串对象。
*   `Day`：是天数。

**返回值：** 此方法返回更新的日期和时间。

**例 1：**

## index.js

```javascript
// Node.js program to demonstrate the
// Date.addDays() method

// Importing module
const date = require('date-and-time')

// Creating object of current date and time
// by using Date()
const now = new Date();

// Adding Days to the existing date and time
// by using date.addDays() method
const value = date.addDays(now, 24);

// Display the result
console.log("updated date and time : " + value)
```

使用以下命令运行 `index.js` 文件：

```bash
node index.js
```

**输出：**

```text
updated date and time :
Wed Mar 31 2021 20:07:07 GMT+0530 (India Standard Time)
```

**例 2：**

## index.js

```javascript
// Node.js program to demonstrate the
// Date.addDays() method

// Importing module
const date = require('date-and-time')

// Creating object of current date and time
// by using Date()
const now = new Date();

now.setDate(20)

// Adding Days to the existing date and time
// by using date.addDays() method
const value = date.addDays(now, 24);

// Display the result
console.log("updated date and time : " + value)
```

使用以下命令运行 `index.js` 文件：

```bash
node index.js
```

**输出：**

```text
updated date and time :
Tue Apr 13 2021 20:09:57 GMT+0530 (India Standard Time)
```

**参考：** [https://github.com/knowledgecode/date-and-time#adddaysdateobj-days](https://github.com/knowledgecode/date-and-time#adddaysdateobj-days)