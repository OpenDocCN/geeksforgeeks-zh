# jQWidgets jqxScrollBar 值更改事件

> 原文：[https://www.geeksforgeeks.org/jqwidgets-jqxscrollbar-valuechanged-event/](https://www.geeksforgeeks.org/jqwidgets-jqxscrollbar-valuechanged-event/)

`jQWidgets` 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。`jqxScrollBar` 用于表示 jQuery 小部件，该部件提供了一个滚动条，该滚动条具有一个滑动的拇指，其位置对应于一个值。

当指定的 `jqxScrollBar` 的值改变时，触发值改变事件。

**语法：**

```javascript
$('#jqxScrollBar').on('valueChanged', function (event)  
{
   var currentValue = event.currentValue;  
   var previousValue = event.previousValue;
});
```

**链接文件：** 从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/)。在 HTML 文件中，找到下载文件夹中的脚本文件。

```html
<link rel="stylesheet" href="jqwidgets/styles/jqx.base.css" type="text/css"/>
<script type="text/javascript" src="scripts/jquery.js"></script>
<script type="text/javascript" src="jqwidgets/jqxcore.js"></script>
<script type="text/javascript" src="jqwidgets/jqxbuttons.js"></script>
```

**示例：** 以下示例说明了 `jQWidgets` `jqxScrollBar` 的 `valueChanged` 事件。

## HTML 示例

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
            jQWidgets jqxScrollBar valueChanged Event
        </h3>
        <div id='jqx_Scroll_Bar'></div>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Scroll_Bar").jqxScrollBar({
                    width: 200,
                    height: 16
                });
                $("#jqx_Scroll_Bar").on('valueChanged',
                                   function (event) {
                    $("#log").html((event.currentValue));
                });
            });
        </script>
    </center>
</body>

</html>
```

### 输出

![](img/e3ffebf61c50e1a84bdbaae08e2e5e35.png)

### 参考
[https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxscrollbar/jquery-scrollbar-api.htm?search=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxscrollbar/jquery-scrollbar-api.htm?search=)