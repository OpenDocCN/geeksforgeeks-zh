# jQWidgets jqxSortable 禁用属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxsortable-disabled-property/](https://www.geeksforgeeks.org/jqwidgets-jqxsortable-disabled-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。 **jqxSortable** 代表一个 jQuery 插件，允许你用鼠标重新排序 HTML 列表或 div 标签中的元素。

**禁用属性**用于检查 jqxSortable 小部件是否被禁用。它接受布尔类型值，默认值为 false。

**语法:**

设置禁用属性:

```html
$('Selector').jqxSortable({ disabled : boolean });
```

返回禁用的属性:

```html
var disabled = $('Selector').jqxSortable('disabled ');
```

**链接文件:**从给定的链接下载 jQWidgets。在 HTML 文件中，找到下载文件夹中的脚本文件:

> <link type="”text/css”" rel="”Stylesheet”" href="”jqwidgets/styles/jqx.base.css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/globalize . js

**示例:**以下示例说明了 jQWidgets 中的 jqxSortable 禁用属性:

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link type="text/css" rel="Stylesheet" 
          href="jqwidgets/styles/jqx.base.css" />
    <script type="text/javascript" 
            src="scripts/jquery-1.11.1.min.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/globalization/globalize.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxsortable.js">
    </script>
</head>

<body>
    <h1 style="color: green">
          GeeksforGeeks 
    </h1>

    <h3>jQWidgets jqxSortable disabled property</h3>

    <div id="sortable">
        <div class='gfg'><li>C</li></div>
        <div><li>C++</li></div>
        <div><li>Python</li></div>
        <div><li>HTML</li></div>
        <div><li>CSS</li></div>
        <div><li>JavaScript</li></div>
    </div>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#sortable").jqxSortable({
               disabled: true
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/4918ad9dfff7159ca53bffb77628d8e8.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxsortable/jquery-sortable-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxsortable/jquery-sortable-api.htm?search=)