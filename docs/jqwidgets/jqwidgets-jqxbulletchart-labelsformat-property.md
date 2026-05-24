# jQWidgets jqxbullethart 标签格式属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxbullethart-labelsformat-property/](https://www.geeksforgeeks.org/jqwidgets-jqxbulletchart-labelsformat-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。jqxBulletChart 代表一个 jQuery 项目符号图小部件，它有两个度量标准，一个主要的和一个比较的，并在许多不同样式的定性范围的上下文中显示它们。

*标签格式*属性用于设置或返回项目符号图表标签格式。它接受字符串类型值，默认值为 null。它的可能值如下

*   “空”:默认值
*   “d”:十进制数
*   “f”:浮点数
*   “n”:整数
*   “c”:货币号码
*   “p”:百分比数字

**语法:**

```html
$('.selector').jqxBulletChart({
    labelsFormat:'c'
});
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【text/JavaScript】src =【scripts/jquery-1 . 11 . 1 . min . js】></脚本>
> <脚本类型=【text/JavaScript】src =【jqwidgets/jqxcore . js】></脚本>
> 脚本类型=【text/JavaScript】src =【jqwidgets/jqxdraw。

**示例:**以下示例说明了 jQWidgets 中的 jqxBulletChart labelsFormat 属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <script type="text/javascript" src="scripts/jquery-1.11.1.min.js">
    </script>
    <script type="text/javascript" src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" src="jqwidgets/jqxdraw.js">
    </script>
    <script type="text/javascript" src="jqwidgets/jqxdata.js"></script>
    <script type="text/javascript" src="jqwidgets/jqxbulletchart.js"></script>
    <script type="text/javascript" src="jqwidgets/jqxtooltip.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxBulletChart labelsFormat Property
        </h3>

        <div id="gfg"></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $('#gfg').jqxBulletChart({
                width: 700,
                height: 100,
                barSize: "60%",
                title: "GeeksforGeeks",
                description: "Computer science portal",
                ranges: [
                    { startValue: 0, endValue: 100, color: "red" },
                    { startValue: 100, endValue: 200, color: "blue" },
                    { startValue: 200, endValue: 300, color: "yellow" }
                ],
                pointer: { value: 250, color: "green" },
                target: { value: 230, color: "green" },
                ticks: { interval: 50 },
                labelsFormat: 'c'
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/d5fed3eb8bf9f61943418e0418eaa62e.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxbullethart/jquery-bullet-chart-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxbulletchart/jquery-bullet-chart-api.htm)