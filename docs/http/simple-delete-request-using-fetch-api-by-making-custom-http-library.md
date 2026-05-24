# 通过定制 HTTP 库使用提取应用编程接口进行简单的删除请求

> 原文:[https://www . geesforgeks . org/simple-delete-request-use-fetch-API-by-making-custom-http-library/](https://www.geeksforgeeks.org/simple-delete-request-using-fetch-api-by-making-custom-http-library/)

**为什么使用 fetch() API 方法？**
**fetch()**方法用于在不刷新页面的情况下向服务器发送请求。它是 **XMLHttpRequest** 对象的替代品。我们将以一个假的包含数组的应用编程接口为例，从该应用编程接口中，我们将通过定制的 HTTP 库获取应用编程接口方法来显示**删除**数据。本教程使用的 API 是:*https://jsonplaceholder.typicode.com/users/2*

**先决条件:**你应该对 HTML、CSS 和 JavaScript 有基本的认知。

**说明:**首先我们需要创建**index.html**文件，并将下面**index.html**文件的代码粘贴到里面。**index.html**文件包括

**library.js** 和 **app.js** 文件在正文标签下方。现在在 **library.js** 文件中，首先创建一个 ES6 类 **DeleteHTTP** ，在该类中有 **async fetch()** 函数**从 api 中删除**数据。等待有两个阶段。首先为**获取()**然后为其响应。无论我们收到什么响应，我们都将其返回到 **app.js** 文件中的调用函数。
现在在 **app.js** 文件中，首先实例化 **DeleteHTTP** 类。然后通过 **http.delete** 原型函数发送网址到 **library.js** 文件。此外，在这方面，有两个承诺需要解决。第一个用于任何响应数据，第二个用于任何错误。

## index.html

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" 
        content="ie=edge">
    <title>DELETE Request</title>
</head>

<body>
    <h1>
        Simple DELETE request using fetch 
        API by making custom HTTP library
    </h1>

    <!-- Including library.js and app.js -->
    <script src="library.js"></script>
    <script src="app.js"></script>
</body>

</html>
```