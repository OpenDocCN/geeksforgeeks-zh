# jquery mobile dialog widget closed text option

> 原文:[https://www . geesforgeks . org/jquery-mobile-dialog-widget-closebtntext-option/](https://www.geeksforgeeks.org/jquery-mobile-dialog-widget-closebtntext-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile Dialog Widget closeBtnText 选项来自定义关闭按钮的文本，这有助于将其翻译成不同的语言。文本在屏幕上不可见，但它被屏幕阅读器读取。默认情况下，关闭按钮显示为仅图标按钮。它接受字符串类型值，默认值为“关闭”。

**语法:**

```html
$( ".selector" ).dialog({
    closeBtnText: string
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
                closeBtnText: "close"
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Dialog Widget closeBtnText Option</h3>
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

![](img/4e6612fef453395463f8f7ec10328fd5.png)

**参考:**[https://API . jquerymobile . com/dialog/# option-closed tntext](https://api.jquerymobile.com/dialog/#option-closeBtnText)