# jQuery 手机弹窗小部件主题选项

> 原文:[https://www . geesforgeks . org/jquery-mobile-popup-widget-theme-option/](https://www.geeksforgeeks.org/jquery-mobile-popup-widget-theme-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。
在本文中，我们将使用 jQuery 移动弹出窗口小部件*主题*选项来设置弹出窗口内容的配色方案。

**语法:**

```html
$("selector").popup({
  theme: "b"
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
            $("#GFG").popup({
                arrow: "t",
                theme: "b"
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Popup Widget theme Option</h3>
        </div>
        <br>

        <center>
            <div role="main" class="ui-content">
                <a href="#GFG" data-rel="popup">
                    GeeksforGeeks
                </a>
                <div data-role="popup" id="GFG">
                    <p>
                        A Computer Science portal for geeks.
                    </p>

                </div>
            </div>
        </center>
    </div>
</body>

</html>
```

**输出:**

![](img/6b5527fc38a654e687f787ab8158495c.png)

**参考:**T2】https://api.jquerymobile.com/popup/#option-theme