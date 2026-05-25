# `Query.prototype[Symbol.asyncIterator]()` 在 Mongoose 中是如何工作的？

> 原文: [https://www.geeksforgeeks.org/how-does-query-prototype-symbol-asynciterator-works-in-mongoose/](https://www.geeksforgeeks.org/how-does-query-prototype-symbol-asynciterator-works-in-mongoose/)

`Query.prototype[Symbol.asyncIterator]()` 函数用于返回一个异步迭代器，用于 `for await...of` 循环。它适用于 `find()` 查询。用户不需要显式调用这个函数，它会被 JavaScript 运行时自动调用。

## 语法

```
Query.prototype[Symbol.asyncIterator]()
```

## 参数
该函数没有任何参数。

## 返回值
该函数返回一个用于 `for await...of` 循环的异步迭代器。

## 安装 Mongoose

```
npm install mongoose
```

安装 `mongoose` 模块后，可以使用命令在命令提示符下检查您的 `mongoose` 版本。

```
npm list mongoose --version
```

## 数据库
这里使用的样本数据库如下所示。

![](img/c39a4a9c77d6e8ab6ef557b5fda6a218.png)

之后，您可以创建一个文件夹并添加一个文件，例如 `index.js`，如下所示。

## 项目结构
项目结构会是这样的。

![](img/3209d9b4369c180282a34be8070d7d6e.png)

## 示例 1

### index.js

```
const mongoose = require('mongoose');

// Database connection
mongoose.connect('mongodb://127.0.0.1:27017/geeksforgeeks', {
    useNewUrlParser: true,
    useCreateIndex: true,
    useUnifiedTopology: true
});

// User model
const User = mongoose.model('User', { 
    name: { type: String },
    age: { type: Number }
});

const Query = User.find(); 
console.log("Value: ", Query[Symbol.asyncIterator])
```

使用以下命令运行 `index.js` 文件:

```
node index.js
```

### 输出

```
Value:  undefined
```

**注意:** 如果 `Symbol.asyncIterator` 未定义，这意味着您的 Node.js 版本不支持异步迭代器。

## 示例 2

### index.js

```
const express = require('express');
const mongoose = require('mongoose');
const app = express()

// Database connection
mongoose.connect('mongodb://127.0.0.1:27017/geeksforgeeks', {
    useNewUrlParser: true,
    useCreateIndex: true,
    useUnifiedTopology: true
});

// User model
const User = mongoose.model('User', { 
    name: { type: String },
    age: { type: Number }
});

const Query = User.find(); 
console.log("Using Express: ", Query[Symbol.asyncIterator])

app.listen(3000, function(error ){
    if(error) console.log(error)
    console.log("Server listening on PORT 3000")
})
```

使用以下命令运行 `index.js` 文件:

```
node index.js
```

### 输出

```
Using Express: undefined
```

## 参考
[https://mongoosejs.com/docs/api/query.html#query_Query-Symbol.asyncIterator](https://mongoosejs.com/docs/api/query.html#query_Query-Symbol.asyncIterator)