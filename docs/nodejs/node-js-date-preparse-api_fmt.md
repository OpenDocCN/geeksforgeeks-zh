# Node.js Date.preparse() API

> 原文：[https://www.geeksforgeeks.org/node-js-date-preparse-api/](https://www.geeksforgeeks.org/node-js-date-preparse-api/)

日期和时间的`date.preparse()`是一个用于操作JS日期和时间模块的极简函数集合，用于按照一定的模式预解析日期。

**所需模块：** 由npm安装模块或在本地使用。

*   通过npm安装。

```js
npm install date-and-time --save
```

*   使用CDN链接。

```js
<script src="/path/to/date-and-time.min.js"></script>
```

**语法：**

```js
preparse(dateString, arg)
```

**参数：** 该方法以下列参数为参数：

*   `Date string`：是一个日期的字符串对象。
*   `arg`：是所需的日期格式。

**返回值：** 该方法返回解析后的日期和时间。

**例1：**

## index.js

```js
// Node.js program to demonstrate the
// Date.preparse() method

// Importing module
const date = require('date-and-time')

// Creating object of current date and time
// by using Date()
const now  =  new Date('07-03-2021');

// Pre parsing the date and time
// by using date.preparse() method
const value = date.preparse(now.toLocaleDateString(),'D/M/YYYY');

// Display the result
console.log(value)
```

使用以下命令运行`index.js`文件：

```js
node index.js
```

**输出：**

```js
{
  Y: 2021,
  M: 3,
  D: 7,
  H: 0,
  A: 0,
  h: 0,
  m: 0,
  s: 0,
  S: 0,
  Z: 0,
  _index: 8,
  _length: 8,
  _match: 3
}
```

**例2：**

## index.js

```js
// Node.js program to demonstrate the
// Date.preparse() method

// Importing module
const date = require('date-and-time')

// Pre parsing the date and time
// by using date.preparse() method
const value = date.preparse('23:14:05 GMT+0900','HH:mm:ss [GMT]Z');

// Display the result
console.log("pre parsed date and time : " + value._length)
```

使用以下命令运行`index.js`文件：

```js
node index.js
```

**输出：**

```js
pre parsed date and time : 17
```

**参考：** [https://github.com/knowledgecode/date-and-time](https://github.com/knowledgecode/date-and-time)