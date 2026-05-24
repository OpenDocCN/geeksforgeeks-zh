# jqwidgets jqxwindow set content()方法

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jqwidgets-jqxwindow-set content-method/

**简介:jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxWindow 用于在应用程序中输入数据或查看信息。

**设置内容()**方法用于设置当前窗口的内容。

**语法:**

```html
$('selector').jqxWindow('setContent', 'content');
```

**参数:**该函数取一个参数，如下图所示:

*   **内容:**这是将被设置为当前窗口内容的指定字符串。

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> 
> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.summer.css”" type="”text/css”">

**示例:**下面的示例说明了 jQWidgets **setContent()** 方法。

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
        $('#jqxwindow').jqxWindow({
          width: 200,
          height: 100
        });
        $("#jqxbutton").jqxButton({
          height: 30
        });
        $('#jqxbutton').click(function() {
          $("#jqxwindow").jqxWindow('setContent', 'Sample Content');
        });
      });
    </script>
  </head>
  <body>
    <center>
      <h1 style="color: green;"> GeeksforGeeks </h1>
      <h3> jQWidgets jqxWindow setContent() Method </h3>
      <input type="button" id="jqxbutton" 
                 value="Invoke the setContent() method" />
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

![](img/744c28172f430150eb29c3f942b0bdd5.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm?search=)