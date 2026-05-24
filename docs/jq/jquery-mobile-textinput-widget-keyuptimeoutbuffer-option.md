# jquery mobile textinput widget keyuptimeoutbuffer option

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-mobile-textinput 小部件-keyuptimeoutbuffer 选项/

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile Textinput Widget key uptime outbuffer Option 来设置从击键发生到调整 textarea 元素大小之间的等待时间(以毫秒为单位)。如果在这段时间内发生了另一次击键，则调整大小会推迟相同长度的另一段时间。

**语法:**

```html
$( ".selector" ).textinput({
    keyupTimeoutBuffer: number
});
```

**CDN 链接:**首先，添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">
> <脚本 src =//code . jquery . com/jquery-1 . 10 . 2 . min . js”></脚本>
> <脚本 src =//code . jquery . com/mobile/1 . 4 . 5/jquery . mobile-1 . 4 . 5 . min . js”></脚本>

**示例:**

## 超文本标记语言

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1">

    <link rel="stylesheet" href=
"//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css">

    <script src="//code.jquery.com/jquery-1.10.2.min.js">
    </script>

    <script src=
"//code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js">
    </script>

    <script>
        $(document).ready(function () {
            $("#GFG").textinput({
                keyupTimeoutBuffer: 150
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>
                jQuery Mobile Textinput Widget 
                keyupTimeoutBuffer Option
            </h3>
        </div>

        <center>
            <div role="main" class="ui-content" style="width: 50%;">
                <label for="GFG">Enter Text:</label>
                <textarea name="Geeks" id="GFG"></textarea>
            </div>
        </center>
    </div>
</body>

</html>
```

**输出:**

![](img/9645afd538f149fd16907b94dd9363d3.png)

**参考:**[https://API . jquerymobile . com/textinput/# option-key uptimeout buffer](https://api.jquerymobile.com/textinput/#option-keyupTimeoutBuffer)