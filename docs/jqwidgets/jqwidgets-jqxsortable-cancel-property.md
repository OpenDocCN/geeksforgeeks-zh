# jQWidgets jqxSortable 取消属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxsortable-cancel-property/](https://www.geeksforgeeks.org/jqwidgets-jqxsortable-cancel-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxSortable** 代表一个 jQuery 插件，允许你使用鼠标对 HTML 列表或[T5】div](https://www.geeksforgeeks.org/div-tag-html/)标签中的元素重新排序。

*取消*属性用于定义项目是否可以拖动。它接受字符串类型的值，默认值是输入、文本区域、按钮、选择、选项。

**语法:**

*   设置*取消*属性。

    ```html
    $('Selector').jqxSortable({ cancel : string});
    ```

*   归还*取消*房产。

    ```html
    var cancel = $('Selector').jqxSortable('cancel');
    ```

**链接文件:**从给定链接下载 **jQWidgets** 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link type="”text/css”" rel="”Stylesheet”" href="”jqwidgets/styles/jqx.base.css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/globalize . js

**示例:**以下示例说明了 jQWidgets 中的 jqxSortable *取消*属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link type="text/css" rel="Stylesheet" 
          href="jqwidgets/styles/jqx.base.css" />
    <script type="text/javascript" 
            src="scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
            src="jqwidgets/globalization/globalize.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxsortable.js"></script>
</head>

<body>
    <h1 style="color:green">
          GeeksforGeeks 
    </h1>
    <h3>jQWidgets jqxSortable cancel property</h3>
    <div id="sortable">
        <div class='gfg'><li>C</li></div>
        <div><li>C++</li></div>
        <div><li>Python</li></div>
        <div><li>HTML</li></div>
        <div><li>CSS</li></div>
        <div><li>JavaScript</li></div>
    </div>

    <script type="text/javascript">
        $(document).ready(function () 
        {
            $("#sortable").jqxSortable({
               cancel: '.gfg'
            });
        });
    </script>
</body>
</html>
```

**输出:**

![](img/fd36851be3e0c2191d2202b59bb0fe9a.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxsortable/jquery-sortable-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxsortable/jquery-sortable-api.htm?search=)