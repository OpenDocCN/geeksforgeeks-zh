# jQWidgets jqxRating 禁用属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxrating-disabled-property/](https://www.geeksforgeeks.org/jqwidgets-jqxrating-disabled-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxRating 表示一个 jQuery 小部件，它显示评级选项来选择评级。此小部件用于配置 jqxRating 小部件项目的大小、图像和显示项目的数量等。

*禁用*属性用于设置或返回评级小部件是否禁用。它接受布尔类型值，默认值为*假*。

**语法:**

设置*禁用*属性。

```html
$('selector').jqxRating({ disabled: Boolean });
```

返回*禁用的*属性。

```html
var disabled = $('selector').jqxRating('disabled');
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS " type = " text/CSS "/>
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all

**示例:**以下示例说明了 jQWidgets jqxRating *禁用的*属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.energyblue.css" type="text/css" />
    <script type="text/javascript" 
        src="scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqx-all.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxrating.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxRating disabled Property
        </h3>

        <div id='jqxRating'></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxRating").jqxRating({
                width: 200,
                height: 35,
                count: 10,
                disabled: true
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/ba6f2fc08bfb19da61f226bb3380114f.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxrating/jquery-rating-入门. htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxrating/jquery-rating-getting-started.htm)