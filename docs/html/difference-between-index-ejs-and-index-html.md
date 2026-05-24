# index . ejs 和 index.ejs 的区别

> 原文:[https://www . geeksforgeeks . org/index-ejs-和-index-html 之间的差异/](https://www.geeksforgeeks.org/difference-between-index-ejs-and-index-html/)

**什么是 [HTML](https://www.geeksforgeeks.org/html-tutorials/) ？**

超文本标记语言用于设计网页的结构和内容。HTML 实际上在技术上不是像 C++、JAVA 或 python 这样的编程语言。它是一种标记语言，最终向浏览器提供声明性指令。当加载一个网页时，浏览器首先读取 HTML 并从中构建 DOM(文档对象模型)树。HTML 由一系列元素组成。

**什么是模板引擎？**

模板引擎是一种工具，使开发人员能够使用普通的 JavaScript 编写 HTML 标记。模板引擎有自己定义的语法或标签，它们将在运行时插入变量或运行一些编程逻辑，并在将其发送到浏览器进行显示之前生成最终的 HTML。

**什么是 EJS？**

EJS 只是代表嵌入式 JavaScript。它是一种简单的模板语言或引擎。EJS 有自己定义的语法和标签。它提供了一种更简单的动态生成 HTML 的方法。

【HTML 与 EJS 的关系:

我们实际上在 EJS 语法中定义了 HTML，并指定了各种数据在页面上的位置和方式。然后模板引擎结合这些数据并运行编程逻辑来生成最终的 HTML 页面。因此，EJS 的任务是根据您定义模板的方式将您的数据插入到网页中，并生成最终的 HTML。

例如，您可以有一个来自数据库的动态数据表，您希望 EJS 根据您的显示规则生成数据表。

**什么时候用 HTML/ EJS？**

它根据你的应用而变化。如果你想渲染一个静态页面，那么你可以选择一个 HTML 文件，如果你想渲染一个动态页面，其中你的数据来自不同的来源，那么你必须选择一个 EJS 文件。

**index . ejs 和 index.html 的区别:**

<figure class="table">

| **HTML 文件** | **EJS file** |
| It is a static web page. | Suitable for dynamic web pages. |
| HTML makup language is used to write HTML files. | JavaScript is used to write EJS files. |
| Written in HTML language. | HTML tags are dynamically generated using JavaScript. |
| Cannot bind dynamic data before sending it to the browser. | The dynamic data will be bound to the template, and then the final output will be sent to the browser. |
| The extension of HTML file is **. html** | The extension of EJS file is **. ejs** |

</figure>

**示例:**假设你有一个显示员工工资的网页。如果你创建了一个静态的 HTML 文件，那么你需要在每次新员工加入或者工资变化的时候重写它。但是，在 EJS，向其中插入动态数据变得太容易了。

**HTML 版本代码:**

## index.html

```html
<!DOCTYPE html>
<html>

<head>
    <title>Employee Salary</title>
    <style>
        table {
            margin: 20% auto;
            border-collapse: collapse;
            border-spacing: 0;
            width: 20%;
            border: 1px solid #ddd;
        }

        th,
        td {
            text-align: left;
            padding: 16px;
        }

        tr:nth-child(even) {
            background-color: #d1d1d1;
        }
    </style>
</head>

<body>
    <table>
        <tr>
            <th> Employee </th>
            <th> Salary </th>
        </tr>
        <tr>
            <td> Sayan Ghosh </td>
            <td> 37000 </td>
        </tr>
        <tr>
            <td> Susmita Sahoo </td>
            <td> 365000 </td>
        </tr>
        <tr>
            <td> Nabonita Santra </td>
            <td> 36000 </td>
        </tr>
        <tr>
            <td> Anchit Ghosh </td>
            <td> 30000 </td>
        </tr>
    </table>
</body>

</html>
```

**输出:**

![](img/873408ab6c01b83d4386f447494e040a.png)

例版本代码:

**第一步:**首先，创建一个 NodeJS 应用程序，安装需要的模块，如***express . js*****和 ***ejs*** 模块。**

****注:**参考[https://www.geeksforgeeks.org/how-to-use-ejs-in-javascript/](https://www.geeksforgeeks.org/how-to-use-ejs-in-javascript/)开始 EJS。**

****第二步:**创建一个 ***index.js*** 文件，这是我们的基本服务器，代码如下。**

## **index.js**

```html
var express = require('express');
var app = express();

// Set EJS as templating engine 
app.set('view engine', 'ejs');

// Employees data
const empSalary = [
    {
        name: "Sayan Ghosh",
        salary: 37000
    },
    {
        name: "Susmita Sahoo",
        salary: 365000
    },
    {
        name: "Nabonita Santra",
        salary: 36000
    },
    {
        name: "Anchit Ghosh",
        salary: 30000
    }
]

app.get('/employee/salary', (req, res) => {

    // Render method takes two parameter
    // first parameter is the ejs file to 
    // render second parameter is an 
    // object to send to the ejs file
    res.render('index.ejs', { empSalary: empSalary });
})

// Server setup
app.listen(3000, function (req, res) {
    console.log("Connected on port:3000");
});
```

****步骤 3:** 创建一个 ***index.ejs*** 文件，并将其放入 ***视图*** 文件夹中，代码如下。**

## **索引. ejs**

```html
<!DOCTYPE html>
<html>
<head>
  <title>Employee Salary</title>
  <style>
    table {
    margin: 20% auto;
    border-collapse: collapse;
    border-spacing: 0;
    width: 20%;
    border: 1px solid #ddd;
  }

  th, td {
    text-align: left;
    padding: 16px;
  }

  tr:nth-child(even) {
   background-color: #d1d1d1;
  }
  </style>
</head>
<body>
    <table>
      <tr>
           <th> Employee </th>
          <th> Salary </th>
      </tr>

      <% empSalary.forEach(emp => { %>
              <tr>
                  <td> <%= emp.name %>
                  <td> <%= emp.salary %>
              </tr>
      <% }); %> 

     </table>
</body>
</html>
```

****步骤 4:** 使用以下命令运行**服务器**:**

```html
node index.js
```

****输出:**现在打开浏览器，转到***http://localhost:3000/员工/工资*** ，会看到如下输出:**

**![](img/873408ab6c01b83d4386f447494e040a.png)**