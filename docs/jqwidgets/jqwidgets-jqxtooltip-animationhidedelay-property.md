# jqwidgets jqxtoltip animation hidedelay 属性

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jqwidgets-jqxtoltip-animation hidedelay-property/

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。jqxTooltip 是一个 jQuery 小部件，用于显示弹出消息。jqxTooltip 小部件可以与任何 HTML 元素结合使用。

**动画隐藏延迟属性**用于设置或返回隐藏时工具提示动画的持续时间。它接受数字/字符串类型的值，默认值为“快速”。

**语法:**

设置动画隐藏延迟属性。

```html
$('Selector').jqxTooltip({ animationHideDelay: Number });
```

返回动画隐藏延迟属性。

```html
var aniHideDelay = $('Selector').jqxTooltip('animationHideDelay');
```

**链接文件:**从给定的链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS ">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js ">jqwidgets/jqxbuttons . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxtooltip . js "></script>

下面的例子说明了 jQWidgets jqxTooltip animationhidedlayer 属性。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.energyblue.css">
    <script type="text/javascript" 
        src="scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqx-all.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src=".jqwidgets/jqxbuttons.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxtooltip.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxTooltip animationHideDelay Property
        </h3>
        <br><br>

        <input type="button" id="jqxBtn" style="background: green;"
            value="GeeksforGeeks" />
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $('#jqxBtn').jqxButton({
                width: 150,
                height: 50
            });

            $("#jqxBtn").jqxTooltip({
                theme: 'energyblue',
                width: 200,
                height: 30,
                position:'top',
                content: 'A computer science portal',
                animationHideDelay: 2000
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/412b4dea45783d72b10a40500094d47c.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtooltip/jquery-tooltip-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtooltip/jquery-tooltip-api.htm)