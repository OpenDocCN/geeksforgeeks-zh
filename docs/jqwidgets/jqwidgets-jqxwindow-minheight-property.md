# jQWidgets jqxWindow 闵八属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxwindow-Minh have-property/](https://www.geeksforgeeks.org/jqwidgets-jqxwindow-minheight-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxWindow** 用于在应用程序中输入数据或查看信息。

**明八**属性用于设置或获取指定窗口的最小高度。

**语法:**

**设置明八属性:**

```html
$('#jqxWindow').jqxWindow({ minHeight: '65px' });  
```

**获取闵八属性:**

```html
var minHeight = $('#jqxWindow').jqxWindow('minHeight'); 
```

**链接文件:**从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . summer . CSS " type = " text/CSS "/>
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 10 . 2 . min . js "></脚本>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "

**示例:**下面的示例说明了 jQWidgets 中的 jqxWindow**minh8**属性。在本例中，minHeight 设置为 250。

## 超文本标记语言

```html
<html>
<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css"/>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.summer.css" type="text/css"/>
    <script type="text/javascript" 
            src="scripts/jquery-1.10.2.min.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxwindow.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxbuttons.js">
    </script>
    <script type="text/javascript">
    $(document).ready(function() {
       $("#jqxwindow").jqxWindow({
        width: 300,
        theme:'energyblue',
        minHeight: 250
      });
    });
    </script>
</head>
<body>
    <center>
      <h1 style="color: green;"> 
        GeeksforGeeks 
      </h1>
      <h3> jQWidgets jqxWindow minHeight Property </h3>
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

![](img/246ff182c5d6cb92e561447b32411e40.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm)