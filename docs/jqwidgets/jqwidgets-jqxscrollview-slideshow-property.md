# jQWidgets jqxScrollView 幻灯片属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxscrollview-slide-property/](https://www.geeksforgeeks.org/jqwidgets-jqxscrollview-slideshow-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxScrollView 是一个 jQuery 小部件，用于查看比设备屏幕上可见区域更宽的内容。可以使用拖动动作或点击/点击 jqxScrollView 小部件底部的按钮来选择特定的元素。

**幻灯片属性**用于设置或返回幻灯片模式是否启用。该模式用于在一个时间间隔内自动改变页面。它接受布尔类型值，默认值为真。

**语法:**

*   设置幻灯片放映属性。

    ```html
    $('selector').jqxScrollView({ slideShow: Boolean });
    ```

*   返回幻灯片属性。

    ```html
    var slideShow = $('selector').jqxScrollView('slideShow');
    ```

**链接文件:**从链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js

下面的例子说明了 jQWidgets 中的 jqxScrollView 幻灯片属性。

**示例:**

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
    <h1 style="color: green;">
        GeeksforGeeks
    </h1>

    <h3>
        jQWidgets jqxScrollView slideShow Property
    </h3>

    <div id="jqxSV">
        <img class="photo" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211116170527/GetHired.png"
            alt="GetHired">
        <img class="photo" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211116170612/hiring.png"
            alt="hiring">
        <img class="photo" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211116170700/upgrade.png"
            alt="upgrade">
        <img class="photo" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211116170745/gethiredgfg.png"
            alt="gethiredgfg">
    </div>

    <script type="text/javascript">
        $(document).ready(function () {
            $('#jqxSV').jqxScrollView({
                width: 450,
                height: 250,
                buttonsOffset: [0, 0],
                slideShow: true
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/058169ff876c1f3d0671c8d217a296dc.png)

**参考:**[https://www . jqwidgets . com/jquery widgets-documentation/documentation/jqxscrollview/jquery-scroll view-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxscrollview/jquery-scrollview-api.htm)