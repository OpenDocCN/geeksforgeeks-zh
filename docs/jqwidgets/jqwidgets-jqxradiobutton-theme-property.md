# jQWidgets jqxRadioButton 主题属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxradiobutton-theme-property/](https://www.geeksforgeeks.org/jqwidgets-jqxradiobutton-theme-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxRadioButton 小部件代表一个 jQuery 单选按钮，用于在一组互斥且相关的选项中进行选择。此小部件用于从选项组中仅选择一个选项。

**主题属性**用于设置或返回 jqxRadioButton 小部件的主题。它接受字符串类型值，默认值为空(" ")。要使用这个属性，首先，我们需要在标题部分包含主题样式表(jqx.energyblue.css)。主题文件包括在“jqx.base.css”文件之后。

**语法:**

设置主题属性。

```html
$('selector').jqxRadioButton({ theme: String });
```

返回主题属性。

```html
var theme = $('selector').jqxRadioButton('theme');
```

**链接文件:**从给定的链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js

下面的例子说明了 jQWidgets jqxRadioButton 主题属性。

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
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqx-all.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxradiobutton.js"></script>

    <style>
        h1,
        h3 {
            text-align: center;
        }

        #GFG,
        #GFG1 {
            width: 100%;
            margin: 0 auto;
        }
    </style>
</head>

<body>
    <h1 style="color: green;">
        GeeksforGeeks
    </h1>

    <h3>
        jQWidgets jqxRadioButton theme Property
    </h3>

    <div id='GFG'>
        Web Technology
    </div>

    <div id='GFG1'>
        Data Structure
    </div>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#GFG, #GFG1").jqxRadioButton({
                width: 200,
                height: 25,
                theme: 'energyblue'
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/7d22e206ad238cf2b79e81afd216cc1e.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxcheckandradio/jquery-radio button-入门. htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxcheckandradio/jquery-radiobutton-getting-started.htm)