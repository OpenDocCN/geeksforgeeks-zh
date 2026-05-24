# jQWidgets jqxRibbon 模式属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxribbon-mode-property/](https://www.geeksforgeeks.org/jqwidgets-jqxribbon-mode-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。 **jqxRibbon** 是一个 jQuery 小部件，可以用作选项卡式工具栏或大型菜单。

***模式*** **属性**用于设置或返回功能区的显示模式。它接受字符串类型值，其默认值为“默认值”。

它的可能值是:

*   **默认值:**描述功能区内容的高度。
*   **弹出:**描述高度，但不包括色带内容。

**语法:**

设置*模式*属性:

```html
$('selector').jqxRibbon({ mode: String });
```

返回*模式*属性:

```html
var mode = $('selector').jqxRibbon('mode');
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js

**示例:**以下示例说明了 jQWidgets jqxRibbon *模式*属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <script type="text/javascript" 
        src="scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqx-all.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxribbon.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxRibbon mode Property
        </h3>
    </center>

    <div id="jqxRibbon" style="margin: auto;">
        <ul>
            <li>GeeksforGeeks</li>
            <li>Web Technology</li>
            <li>Programming Language</li>
        </ul>
        <div>
            <div>
                <h1>GeeksforGeeks</h1>

                <nav>
                    <a href="#">Home</a> |
                    <a href="#">Interview</a> |
                    <a href="#">Languages</a>
                </nav>

                <input type="button" id='jqxBtn' 
                    style="margin-top: 50px;" value="GFG" />
            </div>

            <div>
                <h1>Web Technology</h1>

                <nav>
                    <a href="#">HTML</a> |
                    <a href="#">CSS</a> |
                    <a href="#">JavaScript</a>
                </nav>
            </div>

            <div>
                <h1>Programming Language</h1>

                <nav>
                    <a href="#">C Programming</a> |
                    <a href="#">C++ Programming</a> |
                    <a href="#">Java Programming</a>
                </nav>
            </div>
        </div>
    </div>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxRibbon").jqxRibbon({
                width: 400,
                height: 30,
                mode: 'popup',
                position: "top",
                selectionMode: "click"
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/80b0fff3e0d09ed31a9baadc3e88ea47.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxribbon/jquery-ribbon-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxribbon/jquery-ribbon-api.htm)