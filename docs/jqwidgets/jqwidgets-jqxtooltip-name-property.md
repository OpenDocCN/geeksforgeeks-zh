# jqwidgets jqxtoltip name property

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxtooltip-name-property/](https://www.geeksforgeeks.org/jqwidgets-jqxtooltip-name-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。jqxTooltip 是一个 jQuery 小部件，用于显示弹出消息。jqxTooltip 小部件可以与任何 HTML 元素结合使用。

**名称属性**用于设置或返回工具提示组的名称。此属性用于一次显示一个工具提示。默认情况下，所有工具提示都在一个组中使用。它接受字符串类型值，默认值为”。

**语法:**

设置 name 属性。

```html
$('Selector').jqxTooltip({ name: String });
```

返回 name 属性。

```html
var name = $('Selector').jqxTooltip('name');
```

**链接文件:**从给定的链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS ">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js ">jqwidgets/jqxbuttons . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxtooltip . js "></script>

下面的示例说明了 jQWidgets jqxTooltip 名称属性。

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
            jQWidgets jqxTooltip name Property
        </h3>
        <br><br>

        <input type="button" id="jqxBtn" 
            style="background: green;" 
            value="GeeksforGeeks" />
        <br><br>

        <input type="button" id="jqxBtn1" 
            style="background: green;" 
            value="Geeks" />
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $('#jqxBtn',).jqxButton({
                width: 150,
                height: 50
            });

            $("#jqxBtn").jqxTooltip({
                theme: 'energyblue',
                content: 'A computer science portal',
                position: 'top',
                width: 250,
                height: 30,
                name: 'tooltipGroup'
            });

            $('#jqxBtn1').jqxButton({
                width: 150,
                height: 50
            });

            $("#jqxBtn1").jqxTooltip({
                theme: 'energyblue',
                content: 'Welcome GeeksforGeeks',
                position: 'top',
                width: 250,
                height: 30,
                name: 'tooltipGroup'
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/9c55acb9923e7051fd62012392d1d424.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxtooltip/jquery-tooltip-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtooltip/jquery-tooltip-api.htm)