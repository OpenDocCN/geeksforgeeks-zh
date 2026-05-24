# jQWidgets jqxSlider 模板属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxslider-template-property/](https://www.geeksforgeeks.org/jqwidgets-jqxslider-template-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。jqxSlider 是一个 jQuery 小部件，可以用来创建一个从一系列值中进行选择的滑块。它在外观方面定制了小部件，并提供了许多配置选项。

**模板属性**用于设置或返回模板，作为默认样式的替代。它接受字符串类型值，其默认值为“默认值”。

它的可能值如下。

*   **‘默认’:**是默认模板，其样式取决于“主题”属性值。
*   **【初级】:**设置深蓝色风格，增加视觉重量。
*   **“成功”:**它为成功或积极的行动设置绿色风格。
*   **“警告”:**设置代表警告的橙色样式。
*   **“危险”:**设置代表危险或消极动作的红色样式。
*   **【信息】:**设置蓝色按钮，不绑定语义动作或使用。

**语法:**

设置模板属性。

```html
$('selector').jqxSlider({ template: String });
```

返回模板属性。

```html
var template = $('selector').jqxSlider('template');
```

**链接文件:**从给定的链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS " type = " text/CSS "/>
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxc

下面的例子说明了 jQWidgets jqxSlider 模板属性。

**示例:**

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
        src="jqwidgets/jqxbuttons.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxslider.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxSlider template Property
        </h3>

        <div id='content'>
            <div id='jqxslider'></div>
        </div>
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxslider").jqxSlider({
                theme: 'energyblue',
                template: 'success'
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/5160d6a42af506be84925abf95bccfba.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxslider/jquery-slider-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxslider/jquery-slider-api.htm)