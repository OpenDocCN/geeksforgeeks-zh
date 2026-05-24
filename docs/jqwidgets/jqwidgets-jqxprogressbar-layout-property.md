# jQWidgets jqxProgressBar 布局属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxprogressbar-layout-property/](https://www.geeksforgeeks.org/jqwidgets-jqxprogressbar-layout-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxProgressBar 用于表示 jQuery progressbar 小部件，它直观地指示冗长操作的进度。

**布局属性**用于设置或返回 jqxProgressBar 的布局。它接受字符串类型的值，默认值为“正常”。

它的可能值是–

*   正常
*   “反转”

**语法:**

设置布局属性。

```html
$('selector').jqxProgressBar({ layout: String });
```

返回布局属性。

```html
var layout = $('selector').jqxProgressBar('layout');
```

**链接文件:**从链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js "></脚本>
> 脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js

下面的例子说明了 jQWidgets 中的 jqxProgressBar 布局属性。

**示例:**

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
        src="jqwidgets/jqxprogressbar.js"></script>
    <style>
        h1, h3 {
            text-align: center;            
        }
        #jqxPB {
            margin-left: 40%;
        }
    </style>
</head>

<body>
    <h1 style="color: green;">
        GeeksforGeeks
    </h1>

    <h3>
        jQWidgets jqxProgressBar layout Property
    </h3>

    <div id='jqxPB'></div>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#jqxPB").jqxProgressBar({
                value: 50,
                width: 250,
                height: 30,
                layout: 'reverse'
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/3261638f9f3daddf9251d7b1940d50e5.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxprogressbar/jquery-progressbar-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxprogressbar/jquery-progressbar-api.htm)