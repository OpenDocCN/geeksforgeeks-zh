# jQWidgets jqxProgressBar 值属性

> 原文:[https://www . geeksforgeeks . org/jqwidgets-jqxprogressbar-value-property/](https://www.geeksforgeeks.org/jqwidgets-jqxprogressbar-value-property/)

**简介:** jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxProgressBar 用于表示 jQuery progressbar 小部件，它直观地指示冗长操作的进度。

**值属性**用于设置或返回进度条的值。进度条的值应该介于最小值(默认值:0)和最大值(默认值:100)之间。它接受数字类型值，默认值为 0。

**语法:**

设置 value 属性。

```html
$('selector').jqxProgressBar({ value: Number });
```

返回 value 属性。

```html
var value = $('selector').jqxProgressBar('value');
```

**链接文件:**从链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">

下面的例子说明了 jQWidgets 中的 jqxProgressBar 值属性。

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
        h1,
        h3 {
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
        jQWidgets jqxProgressBar value Property
    </h3>

    <div id='jqxPB'></div>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxPB").jqxProgressBar({
                width: 250,
                height: 30,
                value: 60,
                showText: true
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/72d53b976797f07dc6c94fe9936875d9.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxprogressbar/jquery-progressbar-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxprogressbar/jquery-progressbar-api.htm)