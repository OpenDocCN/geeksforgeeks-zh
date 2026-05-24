# jQWidgets jqxScrollBar 主题属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxscrollbar-theme-property/](https://www.geeksforgeeks.org/jqwidgets-jqxscrollbar-theme-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxScrollBar** 用于表示 jQuery 小部件，该部件提供了一个滚动条，该滚动条具有一个滑动的拇指，其位置对应于一个值。

***主题*** 属性用于设置或获取指定 **jqxScrollBar** 的主题。

**语法:**

*   设置*主题*属性:

    ```html
    $('#jqxScrollBar').jqxScrollBar({ theme: 'energyblue' });
    ```

*   获取*主题*属性:

    ```html
    var theme = $('#jqxScrollBar').jqxScrollBar('theme');
    ```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”/">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS " type = " text/CSS "/>
> <脚本类型= " text/JavaScript " src = " scripts/jquery . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js ">

**示例:**下面的示例说明了 jQWidgets jqxScrollBar ***主题*** 属性。在以下示例中， ***主题*** 属性的值已设置为“*能量值*”。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" 
          href="jqwidgets/styles/jqx.base.css"
          type="text/css"/>
    <script type="text/javascript" 
            src="scripts/jquery.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxbuttons.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxscrollbar.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqx-all.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color:green;">
            GeeksforGeeks
        </h1>
        <h3>
            jQWidgets jqxScrollBar theme Property
        </h3>
        <div id='jqx_Scroll_Bar'></div>
        <input type="button" style="margin: 28px;" 
               id="button_for_theme" 
          value="Value of the theme property"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Scroll_Bar").jqxScrollBar({
                    width: 200,
                    height: 20,
                    theme: 'energyblue'
                });
                $("#button_for_theme").jqxButton({
                    width: 250
                });
                $("#button_for_theme").jqxButton().
                    click(function () {
                        var Value_of_theme =
                            $('#jqx_Scroll_Bar')
                             .jqxScrollBar('theme');
                        $("#log").html((Value_of_theme));
                    });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/139f602a68807ff743b502dbddb7d214.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxscrollbar/jquery-scroll bar-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxscrollbar/jquery-scrollbar-api.htm?search=)