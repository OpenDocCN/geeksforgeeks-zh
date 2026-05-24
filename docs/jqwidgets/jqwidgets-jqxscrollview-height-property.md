# jQWidgets jqxScrollView 高度属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxscrollview-height-property/](https://www.geeksforgeeks.org/jqwidgets-jqxscrollview-height-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxScrollView** 是一个 jQuery 小部件，用于查看比设备屏幕上可见区域更宽的内容。可以使用拖动动作或点击位于 **jqxScrollView** 小部件底部的按钮来选择特定元素。

*高度*属性用于设置或返回 **jqxScrollView** 小部件的高度。它接受数字/字符串类型的值，默认值为 320。

**语法:**

*   设置*高度*属性。

    ```html
    $('selector').jqxScrollView({ height: Number/String });
    ```

*   返回*高度*属性。

    ```html
    var height = $('selector').jqxScrollView('height');
    ```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js

**示例:**下面的示例说明了 jQWidgets 中的 jqxScrollView *高度*属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet"
          href="jqwidgets/styles/jqx.base.css" 
          type="text/css" />
    <script type="text/javascript" 
            src="scripts/jquery-1.11.1.min.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqx-all.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxscrollview.js">
    </script>

    <style>
        h1,
        h3 {
            text-align: center;
        }

        #jqxSV {
            width: 100%;
            margin: 0 auto;
        }
    </style>
</head>

<body>
    <h1 style="color:green;">
        GeeksforGeeks
    </h1>

    <h3>
        jQWidgets jqxScrollView height Property
    </h3>

    <div id="jqxSV">
        <img class="photo" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211116170527/GetHired-300x121.png"
            alt="">
        <img class="photo" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211116170612/hiring-300x115.png"
            alt="">
        <img class="photo"
            src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211116170700/upgrade-300x126.png"
            alt="">
        <img class="photo"
            src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211116170745/gethiredgfg-300x110.png"
            alt="">
    </div>

    <script type="text/javascript">
        $(document).ready(function () {
            $('#jqxSV').jqxScrollView({
                width: 450,
                height: 250,
                buttonsOffset: [0, 0]
            });
        });
    </script>
</body>
</html>
```

**输出:**

![](img/50562763b3eb9334c7041d4d2c0dc5bb.png)

**参考:**[https://www . jqwidgets . com/jquery widgets-documentation/documentation/jqxscrollview/jquery-scroll view-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxscrollview/jquery-scrollview-api.htm)