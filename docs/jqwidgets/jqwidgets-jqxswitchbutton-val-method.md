# jQWidgets jqxSwitchButton val()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxswitchbutton-val-method/](https://www.geeksforgeeks.org/jqwidgets-jqxswitchbutton-val-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxSwitchButton 用于说明一个 jQuery 按钮小部件，它在被单击后会改变其验证状态。此外，它与 jqxToggleButton 完全相同，但拥有独特的用户界面视图。

**val()方法**用于设置或获取值。它有一个可选参数，即布尔类型的值。它返回一个布尔值。

**语法:**

去获取价值。

```html
var value = $("Selector").jqxSwitchButton('val');
```

使用 jQuery 的 val()获取值。

```html
var value = $("Selector").val();
```

设定值。

```html
$("Selector").jqxSwitchButton('val', true);
```

使用 jQuery 的 val()设置值。

```html
$("Selector").val(true);
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【文本/JavaScript】src =【脚本/jquery-1 . 11 . 1 . min . js】></脚本>
> T8】脚本类型=【文本/JavaScript】src =【jqwidgets/jqxcore . js】></脚本>
> <脚本类型=【文本/JavaScript】src =【jqwidgets/jqxbuttons . js】。

下面的例子说明了 jQWidgets 中的 jqxSwitchButton **val()方法**。

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
      <h3>jQWidgets jqxSwitchButton val() method</h3>
      <br />
      <div id="jqxSB"></div>
      <div>
        <input
          type="button"
          id="jqxBtn"
          style="margin-top: 25px"
          value="Setting value"
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
          $("#jqxSB").jqxSwitchButton("val", false);
        });
      });
    </script>
  </body>
</html>
```

**输出:**

![](img/a8e96d4720b2b992fc30e280fa90163f.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-api.htm)