# jQWidgets jqxButton 模板属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxbutton-template-property/](https://www.geeksforgeeks.org/jqwidgets-jqxbutton-template-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxButton 用于说明 jQuery 按钮小部件，它使我们能够在所需的网页上显示按钮。

***模板*** 属性用于指定显示按钮的模板，作为所用默认样式的选项。它的类型为字符串，默认值为“默认值”。

其可能值如下:

*   系统默认值
*   主要的
*   成功
*   警告
*   危险
*   相反的
*   信息
*   环

**语法:**

设置模板属性。

```html
$("#jqxButton").jqxButton({ template: 'primary'});
```

获取模板属性。

```html
var template = $('#jqxButton').jqxButton('template');
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【文本/JavaScript】src =【脚本/jquery-1 . 11 . 1 . min . js】></脚本>
> T8】脚本类型=【文本/JavaScript】src =【jqwidgets/jqxcore . js】></脚本>
> <脚本类型=【文本/JavaScript】src =【jqwidgets/jqxbuttons . js】。

**示例:**以下示例说明了 jQWidgets 中的 jqxButton *模板*属性。

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
      <h3>jQWidgets jqxButton template Property</h3>
      <br />
      <input
        type="button"
        id="jqxBtn"
        style="padding: 5px 20px"
        value="Click here"
      />
      <div id="log"></div>
    </center>

    <script type="text/javascript">
      $(document).ready(function () {
        $("#jqxBtn").jqxButton({
          width: "150px",
          height: "80px",
          template: "info",
        });

        $("#jqxBtn").on("click", function () {
          var temp = $("#jqxBtn").jqxButton("template");
          $("#log").html("Template_name: " + temp);
        });
      });
    </script>
  </body>
</html>
```

**输出:**

![](img/ab5c7fc014ad7ed8f68c42a9297cbe7e.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-api.htm?search=)