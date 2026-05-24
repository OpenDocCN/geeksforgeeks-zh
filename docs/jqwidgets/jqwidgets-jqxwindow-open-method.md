# jQWidgets jqxWindow open()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxwindow-open-method/](https://www.geeksforgeeks.org/jqwidgets-jqxwindow-open-method/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxWindow 用于在应用程序中输入数据或查看信息。

**open()** 方法用于打开或显示当前窗口。此方法不接受任何参数。

**语法:**

```html
$('selector').jqxWindow('open');
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

```html
<link rel="stylesheet" href="jqwidgets/styles/jqx.base.css" type="text/css" />
<link rel="stylesheet" href="jqwidgets/styles/jqx.summer.css" type="text/css" />
<script type="text/javascript" src="scripts/jquery-1.10.2.min.js"></script>
<script type="text/javascript" src="jqwidgets/jqxcore.js"></script>
<script type="text/javascript" src="jqwidgets/jqxwindow.js"></script>
<script type="text/javascript" src="jqwidgets/jqxbuttons.js"></script>
```

**示例:**这个示例说明了 jQWidgets open()方法。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <link rel="stylesheet" href=
          "jqwidgets/styles/jqx.base.css" type="text/css"/>
    <link rel="stylesheet" href=
          "jqwidgets/styles/jqx.summer.css" type="text/css"/>
    <script type="text/javascript" src="scripts/jquery-1.10.2.min.js">
    </script>
    <script type="text/javascript" src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" src="jqwidgets/jqxwindow.js">
    </script>
    <script type="text/javascript" src="jqwidgets/jqxbuttons.js">
    </script>
    <script type="text/javascript">
      $(document).ready(function() {
        $('#jqxwindow').jqxWindow({autoOpen: false,
          width: 200,
          height: 100
        });
        $("#jqxbutton").jqxButton({
          height: 30
        });
        $('#jqxbutton').click(function() {
          $("#jqxwindow").jqxWindow('open');
        });
      });
    </script>
  </head>
  <body>
    <center>
      <h1 style="color: green;"> GeeksforGeeks </h1>
      <h3> jQWidgets jqxWindow open() Method </h3>
      <input type="button" id="jqxbutton" 
                 value="Invoke the open() method" />
      <div id='content'>
        <div id='jqxwindow'>
          <div> Header</div>
          <div>
             <div>GeeksforGeeks</div>
          </div>
        </div>
      </div>
    </center>
  </body>
</html>
```

**输出:**

![](img/4d05dd85d5c5f0b882f272f4c98586ba.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm?search=)