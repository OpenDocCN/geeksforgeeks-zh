# 如何在 Node.js 中实现访客计数器？

> 原文：[https://www.geeksforgeeks.org/how-to-implement-visitor-counter-in-node-js/](https://www.geeksforgeeks.org/how-to-implement-visitor-counter-in-node-js/)

我们将使用 Node.js 中的 `express` 和 `mongoose` 来实现访客计数器。使用 `mongoose` 将计数存储在 `mongoose` 数据库中的好处是，当我们重新启动服务器时，计数不会丢失。每当浏览器获得该页面时，访问者的数量就会增加一（1）。让我们一步一步走过。

**步骤 1：** 创建一个 `app.js` 文件并用 `npm` 初始化你的项目。

```bash
npm init
```

**步骤 2：** 使用 `npm` 安装 `express` 和 `mongoose`。

```bash
npm install express
npm install mongoose
```

`Express` 包将帮助我们创建服务器并为 `GET` 请求定义路由。`mongoose` 是一个针对 MongoDB 和 NodeJS 的对象数据建模库，它将帮助我们与 MongoDB 数据库进行对话。

**项目结构：** 项目结构如下图所示：

![](img/ddd5cd2c39b60066039dac6a1d13e35f.png)

项目结构

**步骤 3：** 让我们开始编写 `app.js` 文件的代码。

1.  首先需要 `express` 和 `mongoose`。
2.  创建到本地 MongoDB 数据库的连接。
3.  定义 `mongoose` 模式来存储记录。它有两个字段：一个是 `String` 数据类型的 `name`，另一个是 `Number` 数据类型的 `count`。
4.  从模式创建 `mongoose` 模型。
5.  定义根 `GET` 请求，让 `app` 监听本地端口。

当应用程序第一次被访问时，`GET` 请求有一种特殊情况。在这种情况下，我们需要创建默认记录，访问者的数量等于 1（1）。对于其他时间，只需将其值增加 1。

我们使用 `mongoose` 的 `findOne()` 函数，该函数以一个参数作为搜索条件。它返回符合我们条件的第一条记录。如果没有记录匹配，则返回一个 `null` 值。现在让我们看看 `app.js` 文件的完整代码。

## app.js

```javascript
// Requiring express to handle routing
const express = require('express')

// Creating app 
const app = express()

// Requiring mongoose to handle mongoDB Database
const mongoose = require('mongoose')

// Connecting to local MongoDB
mongoose.connect("mongodb://localhost:27017/visitCounterDB", {
    useNewUrlParser: true
});

// Creating visitor Schema to hold the
// count of visitors
const visitorSchema = new mongoose.Schema({
    name: String,
    count: Number
})

// Creating Visitor Table in visitCounterDB
const Visitor = mongoose.model("Visitor",visitorSchema)

// Get request to app root
app.get('/', async function(req,res){

    // Storing the records from the Visitor table
    let visitors = await Visitor.findOne({name: 'localhost'})

    // If the app is being visited first
    // time, so no records
    if(visitors == null) {

        // Creating a new default record
        const beginCount = new Visitor({
            name : 'localhost',
            count : 1
        })

        // Saving in the database
        beginCount.save()

        // Sending the count of visitor to the browser
        res.send(`<h2>Counter: `+1+'</h2>')

        // Logging when the app is visited first time
        console.log("First visitor arrived")
    }
    else{

        // Incrementing the count of visitor by 1
        visitors.count += 1;

        // Saving to the database
        visitors.save()

        // Sending the count of visitor to the browser
        res.send(`<h2>Counter: `+visitors.count+'</h2>')

        // Logging the visitor count in the console
        console.log("visitor arrived: ",visitors.count)
    }
})

// Creating server to listen at localhost 3000
app.listen(3000,function(req,res){

    // Logging when the server has started
    console.log("listening to server 3000")
})
```

**步骤 4：** 现在运行应用程序。

```bash
node app.js
```

**输出：** 现在点击 `http://localhost:3000` 在浏览器中加载该应用。

![](img/0432bfe4d059d6fbf1f4afae29192479.png)

输出屏幕

关闭服务器，再次重启后，当我们访问根页面时，我们看到访问者的计数是 `保留` 并增加 1。我们将所有这些步骤记录到控制台中，也是为了验证和理解输出。

![](img/acf158a0257581f6be7423699c2a9579.png)

控制台