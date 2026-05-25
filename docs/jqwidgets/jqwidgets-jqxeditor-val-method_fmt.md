# jQWidgets jqxEditor val()方法

> 原文: [https://www.geeksforgeeks.org/jqwidgets-jqxeditor-val-method/](https://www.geeksforgeeks.org/jqwidgets-jqxeditor-val-method/)

`jQWidgets` 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。`jqxEditor` 用于表示 jQuery HTML 文本编辑器，该编辑器可用于简化网页内容创建，也可用于替代 HTML 文本区域。

## val()方法

`val()`方法用于设置 `jqxEditor` 小部件的值。它将字符串作为输入，并在编辑器中返回包含当前值的字符串。

## 语法

设置编辑器的值

```html
$('Selector').jqxEditor('val', string);  
```

返回编辑器的值

```javascript
var value = $("Selector").val();
```

## 参数

该方法取一个参数，讨论如下:

*   **值:** 是用于设置编辑器值的字符串值。

## 链接文件

从 [https://www.jqwidgets.com/download/](https://www.jqwidgets.com/download/) 链接下载 `jQWidgets`。在 HTML 文件中，找到下载文件夹中的脚本文件:

> <link rel="stylesheet" href="jqwidgets/styles/jqx.base.css" type="text/css">
> <script type="text/javascript" src="scripts/jquery-1.11.1.min.js"></script>
> <script type="text/javascript" src="jqwidgets/jqxcore.js"></script>
> <script type="text/javascript" src="jqwidgets/jqxbuttons.js"></script>
> <script type="text/javascript" src="jqwidgets/jqxscrollbar.js"></script>
> <script type="text/javascript" src="jqwidgets/jqxlistbox.js"></script>
> <script type="text/javascript" src="jqwidgets/jqxdropdownlist.js"></script>
> <script type="text/javascript" src="jqwidgets/jqxdropdownbutton.js"></script>
> <script type="text/javascript" src="jqwidgets/jqxcolorpicker.js"></script>
> <script type="text/javascript" src="jqwidgets/jqxwindow.js"></script>
> <script type="text/javascript" src="jqwidgets/jqxeditor.js"></script>
> <script type="text/javascript" src="jqwidgets/jqxtooltip.js"></script>
> <script type="text/javascript" src="jqwidgets/jqxcheckbox.js"></script>

以下示例说明了 `jQWidgets` 中的 `jqxEditor` `val()`方法:

## 示例

### HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <script type="text/javascript" 
        src="scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxbuttons.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxscrollbar.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxlistbox.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxdropdownlist.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxdropdownbutton.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcolorpicker.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxwindow.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxeditor.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxtooltip.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcheckbox.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>jQWidgets jqxEditor val() Method</h3>
        <textarea id="editor">
        </textarea>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $('#editor').jqxEditor({
                height: "400px",
                width: '800px'
             });
            $('#editor').jqxEditor('val', 'Hi Geeks');
        });
    </script>
</body>
</html>
```

## 输出

![](img/b38439174a316d9c6db35a97e93c4a60.png)

## 参考

[https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxeditor/jquery-editor-api.htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxeditor/jquery-editor-api.htm)