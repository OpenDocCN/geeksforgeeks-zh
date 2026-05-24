# jQWidgets jqxButton 圆角器属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxbutton-roundedcorners-property/](https://www.geeksforgeeks.org/jqwidgets-jqxbutton-roundedcorners-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxButton 用于说明 jQuery 按钮小部件，它使我们能够在所需的网页上显示按钮。

**圆角属性**用于启用或禁用圆角实用程序。此外，它还影响了支持 *CSS* 边框半径的浏览器。它属于字符串类型，默认值为“jqx-rc-all”。

它的可能值是:

*   全部
*   顶端
*   底部
*   左边的
*   正确
*   右上的
*   左上的
*   右下角
*   左下角

**语法:**

设置*圆角*属性。

```html
$("#jqxButton").jqxButton({ roundedCorners: 'jqx-rc-t'});
```

获取*圆规*属性。

```html
var roundedCourners = $('#jqxButton').jqxButton('roundedCorners');
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【文本/JavaScript】src =【脚本/jquery-1 . 11 . 1 . min . js】></脚本>
> T8】脚本类型=【文本/JavaScript】src =【jqwidgets/jqxcore . js】></脚本>
> <脚本类型=【文本/JavaScript】src =【jqwidgets/jqxbuttons . js】。

下面的例子说明了 jQWidgets 中的 jqxButton **roundedCorners** 属性。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" 
          href=
"jqwidgets/styles/jqx.base.css" 
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
        <h1 style="color: green">GeeksforGeeks</h1>
        <h3>jQWidgets jqxButton roundedCorners Property</h3>
        <br />
        <input type="button" id="jqxBtn" 
               style="padding: 5px 20px" 
               value="Click here" />
        <div id="log"></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#jqxBtn").jqxButton({
                width: "100px",
                height: "60px",
                roundedCorners: "top",
            });

            $("#jqxBtn").on("click", function (event) {
                var rc = $("#jqxBtn")
                    .jqxButton("roundedCorners");
                $("#log").html("value: " + rc);
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/ba18880c4a3e68ca4f0fca4bcdb75db6.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-api.htm)