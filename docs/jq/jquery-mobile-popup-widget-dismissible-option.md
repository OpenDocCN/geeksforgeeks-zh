# jQuery 移动弹出窗口小部件可取消选项

> 原文:[https://www . geesforgeks . org/jquery-mobile-popup-widget-disable-option/](https://www.geeksforgeeks.org/jquery-mobile-popup-widget-dismissible-option/)

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile Popup Widget 消除选项来设置消除值，以便在单击弹出窗口之外或按下 Escape 后关闭弹出框。

**语法:**

```html
$("selector").popup({
  dismissible: false
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
                dismissible: false
            });
        });
    </script>
</head>

<body>
    <div data-role="page" id="page1">
        <div data-role="header">
            <h1>GeeksforGeeks</h1>
            <h3>jQuery Mobile Popup Widget dismissible Option</h3>
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

![](img/78c1888a11a1b2f6d95d85405d7bd662.png)

**参考:**T2】https://api.jquerymobile.com/popup/#option-dismissible