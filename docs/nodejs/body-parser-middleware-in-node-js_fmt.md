# Node.js中的Body-Parser中间件

> 原文：[https://www.geeksforgeeks.org/body-parser-middleware-in-node-js/](https://www.geeksforgeeks.org/body-parser-middleware-in-node-js/)

Body-Parser是Node.js的请求体解析中间件。它负责在您处理之前解析传入的请求体。

## 安装Body-Parser模块

1.  您可以访问[安装Body-Parser模块](https://www.npmjs.com/package/body-parser)的链接。您可以使用此命令安装此软件包。

```bash
npm install body-parser
```

2.  安装`body-parser`后，您可以使用命令在命令提示符下检查您的`body-parser`版本。

```bash
npm --version body-parser
```

3.  之后，您可以创建一个文件夹并添加一个文件，例如`index.js`。

```bash
node index.js
```

**文件名：SampleForm.ejs**

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <title>Body-Parser Module Demo</title>
</head>

<body>
    <h1>Demo Form</h1>

    <form action="saveData" method="POST">
        <pre>
            Enter your Email    : <input type="text" name="email"> <br>
            <input type="submit" value="Submit Form">
        </pre>
    </form>
</body>

</html>
```

**文件名：index.js**

## JavaScript

```javascript
const bodyparser = require('body-parser')
const express = require("express")
const path = require('path')
const app = express()

var PORT = process.env.port || 3000

// View Engine Setup
app.set("views", path.join(__dirname))
app.set("view engine", "ejs")

// Body-parser middleware
app.use(bodyparser.urlencoded({extended:false}))
app.use(bodyparser.json())

app.get("/", function(req, res){
    res.render("SampleForm")
});

app.post('/saveData', (req, res) => {
    console.log("Using Body-parser: ", req.body.email)
})

app.listen(PORT, function(error){
    if (error) throw error
    console.log("Server created Successfully on PORT", PORT)
})
```