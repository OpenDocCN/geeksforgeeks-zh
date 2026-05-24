# jQWidgets jqxCheckBox animationhideland 属性

> 原文:[https://www . geeksforgeeks . org/jqwidgets-jqxcheckbox-animation hide delay-property/](https://www.geeksforgeeks.org/jqwidgets-jqxcheckbox-animationhidedelay-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxCheckBox 小部件用于显示允许用户选择或取消选择复选框的复选框。

*动画隐藏延迟*属性用于在取消选中复选框时设置或返回淡入淡出动画的延迟。它接受数字类型的值，默认值为 300。

**语法:**

设置*动画隐藏延迟*属性。

```html
$('selector').jqxCheckBox({ animationHideDelay: 200 });
```

返回*动画隐藏延迟*属性。

```html
var delay = $('selector').jqxCheckBox('animationHideDelay');
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">

**示例:**下面的示例说明了 jQWidgets 中的 jqxCheckBox*animationhiddelay*属性。

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
        src="jqwidgets/jqxcheckbox.js"></script>

    <style>
        body {
            margin-left: 100px;
        }

        .jqxcheckbox {
            margin-left: 50px;
        }
    </style>
</head>

<body>
    <h1 style="color: green;">
        GeeksforGeeks
    </h1>

    <h3>
        jQWidgets jqxCheckBox animationHideDelay Property
    </h3>

    <h4>Select your Web Developement Skills</h4>

    <div class='jqxcheckbox'>HTML</div>
    <div class='jqxcheckbox'>CSS</div>
    <div class='jqxcheckbox'>JavaScript</div>
    <div class='jqxcheckbox'>jQuery</div>
    <div class='jqxcheckbox'>PHP</div>
    <div class='jqxcheckbox'>React</div>

    <script type="text/javascript">
        $(document).ready(function () {

            // Create jqxCheckBox
            $(".jqxcheckbox").jqxCheckBox({
                width: 120,
                height: 25,
                animationHideDelay: 5000
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/c073b9e2f3b5f667c6f01c2dc4b45173.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxcheckandradio/jquery-checkandradio-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxcheckandradio/jquery-checkandradio-api.htm)