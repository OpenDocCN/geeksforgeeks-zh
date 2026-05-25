# Node.js 日期时间 `date.subtract()` 方法

> 原文: [https://www.geeksforgeeks.org/node-js-date-and-time-date-subtract-method/](https://www.geeksforgeeks.org/node-js-date-and-time-date-subtract-method/)

`date.subtract()` 方法用于减去两个日期对象。

**所需模块**: 由 `npm` 安装模块或在本地使用。

*   通过 `npm` 安装。

```js
npm install date-and-time --save
```

*   通过 CDN 链接使用。

```html
<script src="/path/to/date-and-time.min.js"></script>
```

**语法:**

```js
const subtract(date1, date2)
```

**参数:** 该方法以下列参数为参数:

*   `date1`: 是第一个日期对象，用于减去第二个日期。
*   `date2`: 是第二个日期对象。

**返回值:** 此方法返回从 `date1` 中减去 `date2` 的结果对象。

**例 1:**

```js
// Node.js program to demonstrate the
// Date.subtract() method

// Importing date-and-time module
const date = require('date-and-time')

// Creating object of current date and time
// by using Date()
const now = new Date();

// Creating object of given date and time
const date1 = new Date(2015, 0, 1);

// Subtracting the both dates
// by using date.subtract() method
const value = date.subtract(now, date1);

// Display the result
console.log("total days between them "
   + value.toDays())
```

使用以下命令运行 `index.js` 文件:

```bash
node index.js
```

**输出:**

```text
total days between them 2270.3951833333335
```

**例 2:**

```js
// Node.js program to demonstrate the
// Date.subtract() method

// Importing date-and-time module
const date = require('date-and-time')

// Creating object of current date and time
// by using Date()
const now = new Date();

// Setting days in the existing date
now.setDate(20);

// Creating object of given date and time
const date1 = new Date(2015, 0, 1);

// Subtracting the both dates
// by using date.subtract() method
const value = date.subtract(now, date1);

// Display the result
console.log("total days between them " + value.toDays())
```

使用以下命令运行 `index.js` 文件:

```bash
node index.js
```

**输出:**

```text
total days between them 2270.397227997685
```

**参考:** [https://github.com/knowledgecode/date-and-time#subtractdate1-date2](https://github.com/knowledgecode/date-and-time#subtractdate1-date2)