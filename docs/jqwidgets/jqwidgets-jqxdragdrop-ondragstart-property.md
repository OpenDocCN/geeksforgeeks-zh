# jQWidgets jqxDragDrop onDragStart 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxdragdrop-ondragstart-property/](https://www.geeksforgeeks.org/jqwidgets-jqxdragdrop-ondragstart-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxDragDrop 用于表示一个 jQuery 拖放小部件，该部件用于使任何 DOM 元素可拖动。它可以与许多小部件结合使用，如 jqxTree、jqxGrid、jqxListBox 等。

*Ondraggstart*属性用于设置或返回拖动开始时正在执行的回调。接受函数类型值，默认值为*空值*。

**语法:**

设置 *onDragStart* 属性。

```html
$('selector').jqxDragDrop({ onDragStart:  });
```

返回 *onDragStart* 属性。

```html
var onDragStart = $('selector').jqxDragDrop('onDragStart');
```

**链接文件:**从链接下载 [<u>jQWidgets</u>](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">

**示例:**以下示例说明了 jQWidgets 中的 jqxDragDrop *onDragStart* 属性。

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
        src="jqwidgets/jqx-all.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxdragdrop.js"></script>
</head>

<body class='default'>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxDragDrop onDragStart Property
        </h3>

        <div id="res"></div>

        <div style="width: 120px; height: 120px; 
            border: 1px solid black; 
            background-color: green;" id="GFG">

            <div style="display: flex;
                justify-content: center;
                align-items: center;
                height: 100%;">
                Drag me
            </div>
        </div>
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#GFG").jqxDragDrop({
                onDragStart: function() {
                    alert("Dragging Start");
                }
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/9677b0c7cd5d22e822d2349cf5227ff8.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxdragdrop/jquery-drag drop-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxdragdrop/jquery-dragdrop-api.htm)