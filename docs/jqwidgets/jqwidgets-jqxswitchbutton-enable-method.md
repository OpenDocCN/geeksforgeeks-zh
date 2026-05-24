# jQWidgets jqxSwitchButton enable()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxswitchbutton-enable-method/](https://www.geeksforgeeks.org/jqwidgets-jqxswitchbutton-enable-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxSwitchButton** 用于说明一个 jQuery 按钮小部件，点击后会改变其验证状态。此外，它与 jqxToggleButton 完全相同，但拥有独特的用户界面视图。

*启用()*方法用于启用显示的开关按钮。它没有参数，也不返回任何内容。

**语法:**

```html
$('Selector').jqxSwitchButton('enable');
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【文本/JavaScript】src =【脚本/jquery-1 . 11 . 1 . min . js】></脚本>
> T8】脚本类型=【文本/JavaScript】src =【jqwidgets/jqxcore . js】></脚本>
> <脚本类型=【文本/JavaScript】src =【jqwidgets/jqxbuttons . js】。

**示例:**下面的示例说明了 jQWidgets 中的 jqxSwitchButton *enable()* 方法。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <link
      rel="stylesheet"
      href="jqwidgets/styles/jqx.base.css"
      type="text/css"
    />
    <script type="text/javascript" 
        src="scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxbuttons.js"></script>
  </head>
  <body>
    <center>
      <h1 style="color: green">GeeksforGeeks</h1>
      <h3>jQWidgets jqxSwitchButton enable() method</h3>
      <br />
      <div id="jqxSB"></div>
      <div>
        <input
          type="button"
          id="jqxBtn"
          style="margin-top: 25px"
          value="Click here"
        />
      </div>
      <div id="log"></div>
    </center>

    <script type="text/javascript">
      $(document).ready(function () {
        $("#jqxBtn").jqxButton({
          width: "150px",
          height: "40px",
        });

        $("#jqxSB").jqxSwitchButton({
          height: "25px",
          width: "70px",
        });

        $("#jqxSB").jqxSwitchButton("disable");

        $("#jqxBtn").on("click", function () {
          $("#jqxSB").jqxSwitchButton("enable");
          $("#log").html("Button enabled");
        });
      });
    </script>
  </body>
</html>
```

**输出:**

![](img/2036c692dfbd5cb1367990cfb43681e2.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-api.htm?search=)