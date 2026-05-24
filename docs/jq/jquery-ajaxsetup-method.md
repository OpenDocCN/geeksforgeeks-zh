# jQuery | ajaxSetup()方法

> 原文:[https://www.geeksforgeeks.org/jquery-ajaxsetup-method/](https://www.geeksforgeeks.org/jquery-ajaxsetup-method/)

jQuery 中的 **ajaxSetup()方法**用于设置未来 AJAX 请求的默认值。

**语法:**

```html
$.ajaxSetup( {name:value, name:value, ... } )
```

**参数:**

*   **类型:**用于指定请求的类型。
*   **url:** 用于指定发送请求的 url。
*   **用户名:**用于指定在 HTTP 访问认证请求中使用的用户名。
*   **xhr:** 用于创建 XMLHttpRequest 对象。
*   **异步:**默认值为真。它指示请求是否应该异步处理。
*   **beforeSend(xhr):** 这是一个在发送请求之前要运行的函数。
*   **数据类型:**服务器响应的预期数据类型。
*   **错误(xhr，状态，错误):**用于请求失败时运行。
*   **全局:**默认值为真。它用于指定是否为请求触发全局 AJAX 事件句柄。
*   **ifModified:** 默认值为 false。它用于指定只有在响应自上次请求后发生更改时，请求才成功。
*   **jsonp:** 在 jsonp 请求中覆盖回调函数的字符串。
*   **jsoncallback:**用于在 jsonp 请求中指定回调函数的名称。
*   **缓存:**默认值为真。它指示浏览器是否应该缓存请求的页面。
*   **完成(xhr，状态):**这是一个在请求完成时运行的功能。
*   **contentType:** 默认值为:“application/x-www-form-URL encoded”，数据发送到服务器时使用。
*   **上下文:**用于为所有 AJAX 相关的回调函数指定“this”值。
*   **数据:**用于指定发送给服务器的数据。
*   **数据过滤器(数据，类型):**用于处理 XMLHttpRequest 的原始响应数据。
*   **密码:**用于指定在 HTTP 访问认证请求中使用的密码。
*   **processData:** 默认值为真。它用于指定随请求发送的数据是否应转换为查询字符串。
*   **scriptCharset:** 用于指定请求的字符集。
*   **成功(结果、状态、xhr):** 请求成功时运行。
*   **超时:**是请求的本地超时。它以毫秒为单位。
*   **传统:**用于指定是否使用参数序列化的传统风格。

**示例 1:** 本示例使用 ajaxSetup()方法从其他文件中调用数据。
**geeks1_data.txt:** 这个文本文件在 HTML 文件内调用。

> 欢迎来到极客博客

**gfg.html**

```html
<!DOCTYPE html>
<html>

<head> 
    <title>jQuery ajaxSetup() Method</title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>

    <script>
        $(document).ready(function(){
            $("li:parent").css("background-color", "green");
        });
    </script>
</head> 

<body style="text-align:center;">

    <h1 id="geeks1" style="color:green">GeeksForGeeks</h1>
    <h2 id="geeks2">jQuery ajaxSetup() Method</h2>
    <h3></h3>

    <button>Click</button>

    <!-- Script to use ajaxSetup() method -->
    <script>
        $(document).ready(function() {
            $("button").click(function() {
                $.ajaxSetup({url: "geeks1_data.txt",
                            success: function(result) {
                    $("h3").html(result);
                }});
                $.ajax();
            });
        });
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/621677a4a5144095a97be4c93c37a207.png)
*   **点击按钮后:**
    ![](img/2933b8d03d6914f268f7bf4e6700177b.png)

**示例 2:** 此示例说明了 ajaxSetup()方法。

```html
<!DOCTYPE html>
<html>

<head> 
    <title>jQuery ajaxSetup() Method</title>

    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js">
    </script>

    <script>
        $(document).ready(function(){
            $("li:parent").css("background-color", "green");
        });
    </script>
</head> 

<body style="text-align:center;">

    <h1 id="geeks1" style="color:green">GeeksForGeeks</h1>
    <h2 id="geeks2">jQuery ajaxSetup() Method</h2>

    <button>Click</button>

    <!-- Script to use jQuery ajaxSetup() Method -->
    <script>
        $(document).ready(function(){
            $("button").click(function(){
                $.ajaxSetup({url:"geek2_dat.txt", error:function(xhr) {
                    alert("Error: " + xhr.status + " " + xhr.statusText);
                }});
                $.ajax();
            });
        });
    </script>
</body>

</html>
```

**输出:**

*   **点击按钮前:**
    ![](img/621677a4a5144095a97be4c93c37a207.png)
*   **点击按钮后:**
    ![](img/4f592be877c4ea6b4288c9371c6f87c7.png)