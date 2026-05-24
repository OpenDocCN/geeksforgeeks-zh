# jQWidgets jqxProgressBar 颜色范围属性

> 原文:[https://www . geeksforgeeks . org/jqwidgets-jqxprogressbar-color ranges-property/](https://www.geeksforgeeks.org/jqwidgets-jqxprogressbar-colorranges-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxProgressBar 用于表示 jQuery progressbar 小部件，它直观地指示冗长操作的进度。

**颜色范围属性**用于设置或返回不同的颜色段。它接受数组类型值，默认值为空数组[]。

**语法:**

设置颜色范围属性。

```html
$('selector').jqxProgressBar({ colorRanges: [
    { stop: val1, color: cval1 },
    { stop: val2, color: cval2 },
    . . .   
]});
```

返回颜色范围属性。

```html
var colorRanges = $('selector').jqxProgressBar('colorRanges');
```

**链接文件:**从链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">

下面的例子说明了 jQWidgets 中的 jqxProgressBar colorRanges 属性。

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
        jQWidgets jqxProgressBar colorRanges Property
    </h3>

    <div id='jqxPB'></div>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#jqxPB").jqxProgressBar({
                value: 100,
                width: 250,
                height: 20,
                colorRanges: [
                    {stop: 50, color: "green"},
                    {stop: 100, color: "red"}  
                ]
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/dd995574f0a5d8c9379d6ef2b1e567c8.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxprogressbar/jquery-progressbar-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxprogressbar/jquery-progressbar-api.htm)