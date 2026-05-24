# jQWidgets jqxScrollBar 最小属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxscrollbar-min-property/](https://www.geeksforgeeks.org/jqwidgets-jqxscrollbar-min-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。**jqxScrollBar****用于表示 jQuery 小部件，该部件提供了一个滚动条，该滚动条具有滑动的拇指，其位置对应于一个值。**

*****min*** 属性用于设置或获取指定 jqxScrollBar 的最小值。**

****语法:****

*   **设置*分钟*属性:**

    ```html
    $('#jqxScrollBar').jqxScrollBar({ min: 100 });
    ```

*   **要获得*分钟*属性:**

    ```html
    var min = $('#jqxScrollBar').jqxScrollBar('min');
    ```

****链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。**

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”/"> **<脚本类型=“text/JavaScript”src =“scripts/jquery . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxbuttons . js”><**

****示例:**以下示例说明了 jQWidgets jqxScrollBar***min***属性。在以下示例中， ***min*** 属性的值已设置为 100。**

## **超文本标记语言**

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
            jQWidgets jqxScrollBar min Property
        </h3>
        <div id='jqx_Scroll_Bar'></div>
        <input type="button" style="margin:28px;" 
               id="button_for_min" 
               value="Value of the min property"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Scroll_Bar").jqxScrollBar({
                    width: 200,
                    height: 20,
                    min: 100
                });
                $("#button_for_min").jqxButton({
                    width: 250
                });
                $("#button_for_min").jqxButton().click(function () {
                    var Value_of_min =
                        $('#jqx_Scroll_Bar').jqxScrollBar('min');
                    $("#log").html((Value_of_min));
                });
            });
        </script>
    </center>
</body>

</html>
```

****输出:****

**![](img/6ea61ac3181c93db7c803cea45f74498.png)**

****参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxscrollbar/jquery-scroll bar-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxscrollbar/jquery-scrollbar-api.htm?search=)**