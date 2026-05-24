# jQWidgets jqxScrollView forward()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxscrollview-forward-method/](https://www.geeksforgeeks.org/jqwidgets-jqxscrollview-forward-method/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxScrollView 是一个 jQuery 小部件，用于查看比设备屏幕上可见区域更宽的内容。可以使用拖动动作或者点击/点击 jqxScrollView 小部件底部的按钮来选择特定的元素。

**前进()方法**用于导航到下一页。它不接受任何参数，也不返回值。

**语法:**

```html
$("Selector").jqxScrollView('forward');
```

**链接文件:**从链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js

下面的例子说明了 jQWidgets 中的 jqxScrollView forward()方法。

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
        jQWidgets jqxScrollView forward() Method
    </h3>

    <center>
        <input type="button" id="jqxBtn" 
            value="forward() Method" 
            style="padding: 5px 15px; margin: 10px;">
    </center>

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
                buttonsOffset: [0, 0]
            });
            $('#jqxBtn').on('click', function() {
                $("#jqxSV").jqxScrollView('forward');
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/a9eee72980391de8f9ce2215d776e456.png)

**参考:**[https://www . jqwidgets . com/jquery widgets-documentation/documentation/jqxscrollview/jquery-scroll view-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxscrollview/jquery-scrollview-api.htm)