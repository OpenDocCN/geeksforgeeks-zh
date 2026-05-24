# jQuery 移动对话框小部件关闭选项

> 原文:[https://www . geesforgeks . org/jquery-mobile-dialog-widget-closebtn-option/](https://www.geeksforgeeks.org/jquery-mobile-dialog-widget-closebtn-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery 移动对话框小部件关闭选项来设置标题中对话框关闭按钮的位置。它的可能值是–左、右或无。它接受字符串类型值，默认值为“左”。

**语法:**

```html
$( ".selector" ).dialog({
    closeBtn: "none"
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
            $("#GFG").dialog({
                closeBtn: "none"
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Dialog Widget closeBtn Option</h3>
        </div>

        <div role="main" class="ui-content">
            <center><a href="#GFG" data-rel="dialog">Open dialog</a>
            </center>
        </div>
    </div>

    <div data-role="page" id="GFG">
        <div data-role="header">
            <h2>GeeksforGeeks</h2>
        </div>
        <div role="main" class="ui-content">
            <p>A computer science portal</p>
        </div>
    </div>
</body>

</html>
```

**输出:**

![](img/a72d8371f6b6c6cd46df265242d703c9.png)

**参考:**[https://API . jquerymobile . com/dialog/# option-closed TN](https://api.jquerymobile.com/dialog/#option-closeBtn)