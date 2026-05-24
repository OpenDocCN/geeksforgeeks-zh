# jQWidgets jqxButton imgHeight 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxbutton-imgheight-property/](https://www.geeksforgeeks.org/jqwidgets-jqxbutton-imgheight-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxButton** 用于说明 jQuery 按钮小部件，它使我们能够在所需的网页上显示按钮。

*图像高度*属性用于设置或获取显示按钮图像的高度。它属于数字类型，默认值为 16。

**语法:**

设置*仪表板*属性:

```html
$('#jqxButton').jqxButton({imgHeight: 16, imgSrc: 'gfg.png' }); 
```

返回*仪表板*属性:

```html
var imgHeight = $('#jqxButton').jqxButton('imgHeight');
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【文本/JavaScript】src =【脚本/jquery-1 . 11 . 1 . min . js】></脚本>
> T8】脚本类型=【文本/JavaScript】src =【jqwidgets/jqxcore . js】></脚本>
> <脚本类型=【文本/JavaScript】src =【jqwidgets/jqxbuttons . js】。

**示例:**以下示例说明了 jQWidgets 中的 jqxButton *imgHeight* 属性。

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
            src="jqwidgets/jqxbuttons.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <h3>jQWidgets jqxButton imgHeight Property</h3>
        <br />

        <input type="button" id="jqxBtn" 
            style="padding: 5px 20px" value="Click here" />
        <br />

        <div id="log"></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#jqxBtn").jqxButton({
                width: "150px",
                height: "80px",
                imgSrc: 
 "https://media.geeksforgeeks.org/wp-content/uploads/20211012130808/imgsr-200x200.png",
                imgPosition: "left",
                textPosition: "right",
                imgWidth: "40px",
                imgHeight: "30px",
            });

            $("#jqxBtn").on("click", function () {
                var imgh = $("#jqxBtn").jqxButton("imgHeight");
                $("#log").html("Height of button's image: " + imgh);
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/12a846be75106f06322f772ca3e18f64.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-api.htm?search=)