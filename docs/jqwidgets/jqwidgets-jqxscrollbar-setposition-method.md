# jQWidgets jqxScrollBar 设置位置()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxscrollbar-set position-method/](https://www.geeksforgeeks.org/jqwidgets-jqxscrollbar-setposition-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxScrollBar** 用于表示 jQuery 小部件，该部件提供了一个滚动条，该滚动条具有一个滑动的拇指，其位置对应于一个值。

**setPosition()** 方法用于为指定的 jqxScrollBar 小部件设置拇指的位置。

**语法:**

```html
$('#jqxScrollBar').jqxScrollBar('setPosition', index); 
```

**参数:**该方法接受如下所示的参数:

*   **指数:**这是新仓位的指数。

**返回值:**此方法不返回值。

**链接文件:**从给定链接下载https://www.jqwidgets.com/download/。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”/">
> <脚本类型=“text/JavaScript”src =“scripts/jquery . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxbuttons . js”><

**示例:**下面的示例说明了 jQWidgets jqxScrollBar**set position()**方法。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet"
          href="jqwidgets/styles/jqx.base.css"
          type="text/css" />
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
            jQWidgets jqxScrollBar setPosition() Method
        </h3>

        <div id='jqx_Scroll_Bar'></div>

        <input type="button" style="margin: 28px;" 
            id="button_for_setPosition"
            value="Set the thumb's position to 600" />

        <div id="log"></div>

        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Scroll_Bar").jqxScrollBar({
                    width: 200,
                    height: 20
                });
                $("#button_for_setPosition").jqxButton({
                    width: 250
                });
                $("#button_for_setPosition").jqxButton().
                    click(function () {
                        $('#jqx_Scroll_Bar').
                            jqxScrollBar(
                                'setPosition', 600);
                    });
            });
        </script>
    </center>
</body>

</html>
```

**输出:**

![](img/dc607697332088b7dbec96370e646fc6.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxscrollbar/jquery-scroll bar-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxscrollbar/jquery-scrollbar-api.htm?search=)