# jQWidgets jqxSwitchButton 取消勾选()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxswitchbutton-uncheck-method/](https://www.geeksforgeeks.org/jqwidgets-jqxswitchbutton-uncheck-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxSwitchButton 用于说明一个 jQuery 按钮小部件，它在被单击后会改变其验证状态。此外，它与 jqxToggleButton 完全相同，但拥有独特的用户界面视图。

**取消选中()方法**用于取消选中显示的按钮。它没有参数，也不返回任何东西。

**语法:**

```html
$('Selector').jqxSwitchButton('uncheck');
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【文本/JavaScript】src =【脚本/jquery-1 . 11 . 1 . min . js】></脚本>
> T8】脚本类型=【文本/JavaScript】src =【jqwidgets/jqxcore . js】></脚本>
> <脚本类型=【文本/JavaScript】src =【jqwidgets/jqxbuttons . js】。

以下示例说明了 jQWidgets 中的 jqxSwitchButton **取消选中()方法**。

**示例:**

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
      <h3>jQWidgets jqxSwitchButton uncheck() method</h3>
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
          checked: true,
        });

        $("#jqxBtn").on("click", function () {
          $("#jqxSB").jqxSwitchButton("uncheck");
        });
      });
    </script>
  </body>
</html>
```

**输出:**

![](img/9a90adb36930aa84d051cf3c5b160607.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-api.htm)