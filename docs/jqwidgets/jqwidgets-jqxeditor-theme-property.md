# jQWidgets jqxEditor 主题属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxeditor-theme-property/](https://www.geeksforgeeks.org/jqwidgets-jqxeditor-theme-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxEditor** 用于表示 jQuery HTML 文本编辑器，可用于简化网页内容创建，也可用于替代 HTML 文本区域。

**主题属性**用于设置或返回编辑器元素的主题。即可以使用该属性设置编辑器的主题。它接受字符串类型值，默认值为”。

**语法:**

设置*主题*属性。

```html
$('Selector').jqxEditor({ theme: 'energyblue'});  
```

返回*主题*属性。

```html
var theme = $('Selector').jqxEditor('theme');
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件:

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS " type = " text/CSS "/ >
> <脚本类型=“text/JavaScript”src =“scripts/jquery-1 . 11 . 1 . min . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxcore . js”></script>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxbuttons” >
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxeditor . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqxtooltip . js”></脚本>
> <脚本类型=“text/JavaScript”src =“jqwidgets/jqqd

以下示例说明了 jQWidgets 中的 jqxEditor **主题属性**:

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
<head>
       <link rel="stylesheet"
          href="jqwidgets/styles/jqx.base.css" 
          type="text/css" />
      <link rel="stylesheet"
          href="jqwidgets/styles/jqx.energyblue.css"
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
    <script type="text/javascript" 
            src="jqwidgets/jqxscrollbar.js">
      </script>
    <script type="text/javascript" 
               src="jqwidgets/jqxlistbox.js">
      </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxdropdownlist.js">
      </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxdropdownbutton.js">
      </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcolorpicker.js">
      </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxwindow.js">
      </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxeditor.js">
      </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxtooltip.js">
      </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcheckbox.js">
  </script>
</head>

<body>
    <center>
        <h1 style="color: green;">
              GeeksforGeeks
          </h1>

        <h3>jQWidgets jqxEditor theme Property</h3>
        <textarea id="editor">
        </textarea>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $('#editor').jqxEditor({
                height: "400px",
                width: '700px',
                theme: 'energyblue'
            });
        });
    </script>

</body>
</html>
```

**输出:**

![](img/3c7ce6570310a3af91a1d874f21c864c.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxeditor/jquery-editor-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxeditor/jquery-editor-api.htm)