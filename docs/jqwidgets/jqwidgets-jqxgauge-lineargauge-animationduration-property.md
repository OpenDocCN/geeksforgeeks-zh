# jQWidgets jqxGauge linear gauge animation duration 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxgauge-linear gauge-animation duration-property/](https://www.geeksforgeeks.org/jqwidgets-jqxgauge-lineargauge-animationduration-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxGauge 代表一个 jQuery gauge 小部件，它是一个值范围内的指示器。我们可以使用仪表来显示数据区域中一系列值中的一个值，有两种类型的仪表:径向仪表和线性仪表。在**线性仪表**中，数值由一些数值以垂直方式线性表示。

**动画持续时间属性**用于设置或返回动画持续时间属性，即用于设置线性标尺值将改变的动画持续时间。它接受数字类型值，默认值为 1000。

**语法:**

设置动画持续时间属性。

```html
$('Selector').jqxLinearGauge({ animationDuration : number });  
```

返回动画持续时间属性。

```html
var anDur = $('Selector').jqxLinearGauge('animationDuration');
```

**链接文件:**下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxchart . js

**示例:**下面的示例说明了 jQWidgets 中的 jqxLinearGauge animationDuration 属性。

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
          src="jqwidgets/jqxcore.js"></script>
  <script type="text/javascript" 
          src="jqwidgets/jqxchart.js"></script>
  <script type="text/javascript" 
          src="jqwidgets/jqxgauge.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
          GeeksforGeeks
        </h1>

        <h3>jQWidgets jqxLinearGauge animationDuration property</h3>

        <div id="gauge"></div>
        <hr>
        <button id = 'btn'>Animate</button>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#gauge").jqxLinearGauge({
                value: 0,
                animationDuration: 1200
            });

        });
        $("#btn").click(function () {
            $('#gauge').jqxLinearGauge({
                value: 30
            });
        });

    </script>
</body>
</html>
```

**输出:**

![](img/e93f2b81be67c0adf1ca980bc7b0ce7e.png)

**参考:**[**https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxgauge/jquery-gauge-API . htm？搜索=**](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxgauge/jquery-gauge-api.htm?search=)