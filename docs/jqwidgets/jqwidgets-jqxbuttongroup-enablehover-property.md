# jQWidgets jqxButtonGroup enableHover 属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxbuttongroup-enable hover-property/](https://www.geeksforgeeks.org/jqwidgets-jqxbuttongroup-enablehover-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxButtonGroup** 用于说明 jQuery 小部件，该部件生成一组功能类似于普通按钮、单选按钮或复选框的按钮。

**启用悬停属性**用于启用或禁用显示的 jqxButtonGroup 的高亮状态。它属于布尔类型，默认值为假。

**语法:**

设置*启用悬停*属性。

```html
$('#Selector').jqxButtonGroup({enableHover: true });
```

返回*启用悬停*属性。

```html
var enableHover = 
    $('#Selector').jqxButtonGroup('enableHover');
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【文本/JavaScript】src =【脚本/jquery-1 . 11 . 1 . min . js】></脚本>
> T8】脚本类型=【文本/JavaScript】src =【jqwidgets/jqxcore . js】></脚本>
> <脚本类型=【文本/JavaScript】src =【jqwidgets/jqxbuttons . js】。

下面的例子说明了 jQWidgets 中的 jqxButtonGroup **enableHover 属性**。

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
        src="jqwidgets/jqxbuttons.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green">
            GeeksforGeeks
        </h1>

        <h3>jQWidgets jqxButtonGroup 
            enableHover property</h3>
        <br />

        <div id="jqxBG">
            <button style="padding: 6px 36px" 
                    id="l">
                ON
            </button>

            <button style="padding: 6px 36px"
                    id="c">
                Button
            </button>

            <button style="padding: 6px 36px"
                    id="r">
                OFF
            </button>
        </div>

        <div>
            <input type="button" id="jqxBtn" 
                   style="margin-top: 25px" 
                   value="Click here" />
        </div>

        <div id="log"></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#jqxBtn").jqxButton({
                width: "100px",
                height: "30px",
            });
            $("#jqxBG").jqxButtonGroup({
                enableHover: true,
            });

            $("#jqxBtn").on("click", function () {
                var eh =
                    $("#jqxBG").jqxButtonGroup("enableHover");
                $("#log").text("Hover state enabled: " + eh);
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/e09078ed4d3e32e3c0e948f9977582fb.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-api.htm)