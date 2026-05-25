# Node.js Date.format() API

> 原文：[https://www.geeksforgeeks.org/node-js-date-format-api/](https://www.geeksforgeeks.org/node-js-date-format-api/)

`Date.format()` 是操作 JS 日期和时间模块的极简函数集合，用于按照一定的模式格式化日期。

**所需模块：** 由 npm 安装模块或在本地使用。

*   通过 npm 安装。

```js
npm install date-and-time --save
```

*   使用 CDN 链接。

```html
<script src="/path/to/date-and-time.min.js"></script>
```

**语法：**

```js
format(dateObj, formatString[, utc])
```

**参数：** 该方法以下列参数为参数：

*   `dateobj`：日期对象。
*   `Format string`：用于显示日期的新字符串格式。

**返回值：** 此方法返回格式化的日期和时间。

### 示例 1

```js
// Node.js program to demonstrate the
// Date.format() method

// Importing module
const date = require('date-and-time')

// Creating object of current date and time
// by using Date()
const now = new Date();

// Formating the date and time
// by using date.format() method
const value = date.format(now,'YYYY/MM/DD HH:mm:ss');

// Display the result
console.log("current date and time : " + value)
```

使用以下命令运行 `index.js` 文件：

```bash
node index.js
```

**输出：**

```text
current date and time : 2021/03/07 12:13:46
```

### 示例 2

```js
// Node.js program to demonstrate the
// Date.format() method

// Importing module
const date = require('date-and-time')

// Formatting the date and time
// by using date.format() method
const value = date.format((new Date('December 17, 1995 03:24:00')),
  'YYYY/MM/DD HH:mm:ss');

// Display the result
console.log("date and time : " + value)
```

使用以下命令运行 `index.js` 文件：

```bash
node index.js
```

**输出：**

```text
date and time : 1995/12/17 03:24:00
```

**参考：** [https://github.com/knowledgecode/date-and-time](https://github.com/knowledgecode/date-and-time)