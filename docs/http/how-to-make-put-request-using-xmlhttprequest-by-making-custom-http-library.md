# 如何通过制作自定义 HTTP 库，使用 XMLHttpRequest 进行 PUT 请求？

> 原文:[https://www . geesforgeks . org/如何使用-xmlhttprequest-by-making-custom-http-library/](https://www.geeksforgeeks.org/how-to-make-put-request-using-xmlhttprequest-by-making-custom-http-library/)

任务是展示如何通过定制 HTTP 库将 **XMLHttpRequest** 用于 **PUT/Update** 数据到一个应用编程接口。我们将以一个包含对象数组的假应用编程接口为例，通过定制的 HTTP 库，我们将通过 **XMLHttpRequest** 方法向 PUT 数据展示该应用编程接口。
**使用的 API:**[https://jsonplaceholder.typicode.com/posts/5](https://jsonplaceholder.typicode.com/posts/5)
**什么是 Ajax？**
**异步** JavaScript 和 XML，用于与服务器进行通信而无需刷新网页从而增加用户体验和更好的性能。要阅读更多关于 Ajax 的内容，请点击[https://www.geeksforgeeks.org/ajax-introduction/.](https://www.geeksforgeeks.org/ajax-introduction/.)
**先决条件:**仅需要 HTML、CSS 和 JavaScript 的基本知识。
**注意:**首先制作一个 HTML 文件，根据需求添加 HTML 标记。在 body 标签的底部，以相同的顺序附加两个脚本文件，如 library.js 和 app.js。
**制作 library.js 文件所需的步骤:**

1.  **library.js** 文件制作一个函数 **easyHTTP** 来初始化一个**新的 XMLHttpRequest()** 方法。
2.  设置 **easyHTTP.prototype.put** 为一个包含三个参数**“URL”、数据和回调的函数。**
3.  现在使用**这个. http.open** 函数打开一个对象。它需要三个参数，第一个是请求类型(GET 或 POST 或 PUT 或 DELETE)，第二个是 API 的 URL，最后一个是布尔值(true 表示异步调用，false 表示同步调用)。
4.  现在我们使用 **onload** 功能显示数据。但在此之前，我们首先需要用**this . http . setrequestheader**方法设置内容类型，并且还要将**这个**关键字分配给**自己**，使**这个**关键字的范围进入 **onload** 功能。 **onload** 函数在完成 API 调用后执行。该函数将运行一个**回调**函数，该函数有两个参数，即**错误**和**响应文本**。
5.  最后一步是使用 **send()** 功能发送请求。这里需要注意的是， **send()** 函数使用 **JSON.stringify(数据)将对象数据转换为字符串后需要发送数据。**

**制作 app.js 文件所需的步骤:**

1.  首先用**新的**关键字实例化 **easyHTTP** 。
2.  创建自定义数据(对象)来放置/更新数据。
3.  在**放**原型函数中传递**网址**、**数据**和一个**回调**函数。
4.  回调函数包含两个参数**错误**如果出现错误就打印，以及**响应得到实际响应。**

**文件名:index.html**

## 超文本标记语言

```htmlhtml
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">
    <title>Put request</title>
</head>
<body>
    <h1>
        Put request using xmlhttpRequest/Ajax
        by making custom HTTP library.
    </h1>
    <div class="result"></div>

    <!-- Including library.js and app.js files -->
    <script src="library.js"></script>
    <script src="app.js"></script>
</body>

</html>
```