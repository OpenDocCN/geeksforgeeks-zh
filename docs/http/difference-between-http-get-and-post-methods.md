# 【HTTP GET 和 POST 方法的区别

> 原文:[https://www . geesforgeks . org/http-get-and-post-methods 之间的区别/](https://www.geeksforgeeks.org/difference-between-http-get-and-post-methods/)

**HTTP GET:** 超文本传输协议(HTTP) Get 方法主要用于客户端(浏览器)端，向指定的服务器发送请求，获取一定的数据或资源。使用这种方法，服务器应该只让我们接收数据，而不改变它的状态。因此，它仅用于查看某些内容，而不是更改它。Get 方法是最常用的 HTTP 方法之一。get 方法的请求参数被附加到 URL。Get 请求对于不需要安全的数据更好(指不包含图像或 word 文档的数据)。

**示例:**在下面的 HTML 代码中，我们创建了一个文本字段为用户名和城市的表单。我们还包括了一个 PHP 文件 getmethod.php，我们的数据将在我们点击提交按钮后发送。

## index.html

```html
<!DOCTYPE html>
<html>

<body>
    <form action="getmethod.php" method="GET">
        Username: <input type="text" 
            name="username" /> <br>

        City: <input type="text" 
            name="city" /> <br>

        <input type="submit" />
    </form>
</body>

</html>
```

在下面使用 GET 方法的 PHP 代码中，我们显示了用户名和城市。

## getmethod.php

```html
<!DOCTYPE html>
<html>

<body>
    Welcome
    <?php echo $_GET["username"]; ?> </br>
    Your City is:
    <?php echo $_GET["city"]; ?>
</body>

</html>
```

**输出:**GET 方法传入的数据在地址栏中清晰可见，会危及安全性。

![](img/6781943dd7a3fcfd4f9f36fb2abb4b30.png)

**HTTP POST:** 超文本传输协议(HTTP) Post 方法主要用于客户端(浏览器)端，将数据发送到指定的服务器，以创建或重写特定的资源/数据。发送到服务器的数据存储在 HTTP 请求的请求体中。Post 方法最终导致新资源的创建或现有资源的更新。由于这种动态使用，它是最常用的 HTTP 方法之一。它不是最安全的方法之一，因为发送的数据包含在请求的正文中，而不是 URL 中。对于需要安全的数据(指包含图像或文字文档的数据)，Post 请求更好。

**示例:**在下面的 HTML 代码中，我们创建了一个表单，其中的文本字段为用户名和研究区域。我们还包括了一个 PHP 文件 postmethod.php，我们的数据将在我们点击提交按钮后发送。

## index.html

```html
<!DOCTYPE html>
<html>

<body>
    <form action="postmethod.php" method="post">
        Username: <input type="text" 
            name="username" /> <br>

        Area of Study: <input 
            type="text" name="area" /> <br>

        <input type="submit" />
    </form>
</body>

</html>
```

在下面使用 POST 方法的 PHP 代码中，我们显示了用户名和研究区域。

## postmethod.php

```html
<!DOCTYPE html>
<html>

<body>
    Welcome
    <?php echo $_POST["username"]; ?> </br>
    YOur Area of Study is:
    <?php echo $_POST["area"]; ?>
</body>

</html>
```

**输出:**POST 方法传入的数据不在地址栏显示，维护了安全性。

![](img/5c307df2e10e816416d96545cd66cc73.png)

**HTTP GET 与 HTTP POST 的区别**

<figure class="table">

| **HTTP GET** | **HTTP POST** |
| In the GET method, we can't send a large amount of data, but send limited data, because the request parameters are appended to the URL. | In the POST method, a large amount of data can be sent because the request parameters are attached to the body. |
| GET 请求相对比 Post 更好，所以它比Post 请求使用得更多。 | POST request is relatively inferior to Get request, so its usage rate is lower than Get request. |
| The security of the GET request is relatively low because the data is exposed in the URL column. | POST requests are relatively more secure because the data is not disclosed in the URL column. |
| Requests made through the GET method are stored in the browser history. | Requests made through POST are not stored in browser history. |
| GET method requests can be saved as bookmarks in the browser. | POST method requests cannot be saved as bookmarks in the browser. |
| Requests made through the GET method are stored in the Browser's cache. | Requests made through POST are not stored in the browser's cache. |
| The data passed through the GET method can be easily stolen by attackers. | The data transmitted through the POST method is not easy to be stolen by attackers. |
| Only ASCII characters are allowed in the GET method. | In the POST method, all types of data are allowed. |

</figure>