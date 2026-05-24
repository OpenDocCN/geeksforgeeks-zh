# jQWidgets jqxExpander rtl 物业

> 原文:[https://www . geeksforgeeks . org/jqwidgets-jqxexpander-RTL-property/](https://www.geeksforgeeks.org/jqwidgets-jqxexpander-rtl-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它非常强大，经过优化，独立于平台，并得到广泛支持。jqxExpander 表示一个 jQuery 小部件，显示标题和内容部分。单击标题部分展开或折叠内容。

***【RTL】*****属性**用于设置或返回是否启用从右向左支持。接受布尔类型值，默认值为*假*。

**语法:**

设置 *rtl* 属性。

```html
$('selector').jqxExpander({ rtl: Boolean });
```

归还 *rtl* 房产。

```html
var rtl = $('selector').jqxExpander('rtl');
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS " type = " text/CSS "/>
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all

**示例:**以下示例说明了 jQWidgets jqxExpander *rtl* 属性。

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
        src="jqwidgets/jqxexpander.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxExpander rtl Property
        </h3>

        <div id='jqxExp'>
            <div>GeeksforGeeks</div>

            <div style="text-align: justify;">
                A Computer Science portal for geeks. 
                It contains well written, well thought 
                and well explained computer science 
                and programming articles, ...
            </div>
        </div>
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxExp").jqxExpander({ 
                width: 250, 
                height: 150,
                rtl: true
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/65c10b85e71fda4c0bb7f82587790a4c.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxexpander/jquery-expander-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxexpander/jquery-expander-api.htm)