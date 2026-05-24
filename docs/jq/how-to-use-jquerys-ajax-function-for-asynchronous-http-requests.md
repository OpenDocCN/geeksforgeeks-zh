# 异步 HTTP 请求如何使用 jQuery 的 ajax()函数？

> 原文:[https://www . geeksforgeeks . org/how-use-jquerys-Ajax-function-for-asynchronous-http-requests/](https://www.geeksforgeeks.org/how-to-use-jquerys-ajax-function-for-asynchronous-http-requests/)

在本文中，我们将看到如何使用 **jQuery 的 ajax()** 函数异步调用后端函数，或者换句话说，HTTP Requests。 **AJAX** 是客户端框架和库使用的一组 web 开发技术，用于对服务器进行异步 HTTP 调用。AJAX 代表“ **A** 同步 **J** avaScript 和 **X** ML”。

简单来说，你可以使用 Ajax 从后端**加载数据**，而不需要实际的页面重载。您也可以在后台**向服务器**发送数据，**请求**数据，**在页面已经加载时接收**数据。使用 ajax 给应用程序带来了更好的用户体验。

**语法:**

```html
$.ajax(url);
$.ajax(url,[options]);
```

下表列出了 ajax 请求下常用的**选项**。

<figure class="table">

| **url** | 一个字符串，包含请求发送到的网址。 |
| **型** | 一种 http 请求，例如 POST、PUT 和 GET。默认为 GET 请求。 |
| content type | 包含发送到服务器的内容类型的字符串。 |
| **数据类型** | 您期望从服务器返回的数据类型，如 JSON、XML 等。 |
| **成功** | 当 Ajax 请求成功时要执行的回调函数。 |
| **错误** | 请求失败时要执行的回调函数。 |
| **数据** | 要发送到服务器的数据。它可以是 JSON 对象、字符串或数组。 |

</figure>

**创建一个简单的 AJAX 获取请求**

在使用 Ajax 之前，我们需要在您的应用程序中获取 jQuery。在本文中，我们将使用在线提供的 Ajax jQuery 脚本，如下面的代码所示。出于本文的目的，我们将考虑一个 JSON 文件，我们将在其中发送一个 ajax()请求并从该文件中检索数据。

让我们考虑名为**“data . JSON”**的 JSON 文件位于名为 **data** 的文件夹中，该文件夹位于**根目录**中，或者换句话说，我们的 html 文件当前所在的文件夹具有如下所示的数据。

**注意:**请记住，您需要在 localhost 或某个已部署的路径上，ajax 请求才能工作，否则会出现 CORS(跨来源资源共享)错误。

**数据文件:**

```html
[
    {
        "Name":"Aman Prakash Jha",
        "Occupation": "Student"
    },
    {
        "Name":"Sharan Swaroop",
        "Occupation":"SDE-1"
    },
    {
        "Name":"Chiraag Kakar",
        "Occupation":"Sr. Software Engineer"
    }
]
```

**示例:**

## HTML

```html
<!DOCTYPE html>
<html>

<head>

    <!--Loading the script so that we can use Ajax-->
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>
</head>

<body>
    <h2>Welcome To GFG</h2>

    <p>
        Default code has been 
        loaded into the Editor.
    </p>

    <button id="getData">GET</button>

    <script>
        $("#getData").click(function (event) {
            event.preventDefault();
            $.ajax({
                url: "data/data.json",
                type: "GET",
                dataType: "json",
                success: function (data) {

                    // This here will print the
                    // retrieved json on the console.
                    console.log(data);
                },
                error: function () {
                    console.log("Something went wrong");
                },
            });
        });
    </script>
</body>

</html>
```