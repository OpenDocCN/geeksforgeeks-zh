# jQWidgets jqxSortable 追加属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxsortable-appendo-property/](https://www.geeksforgeeks.org/jqwidgets-jqxsortable-appendto-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。 **jqxSortable** 代表一个 jQuery 插件，允许你使用鼠标对 HTML [列表](https://www.geeksforgeeks.org/html-lists/)或[标签中的元素重新排序。](https://www.geeksforgeeks.org/div-tag-html/)

***【追加到】*** 属性用于定义拖动过程中鼠标移动的辅助对象被追加到的位置。它接受字符串类型值，默认值为“parent”。

**语法:**

*   设置属性的*附录。

    ```html
    $('Selector').jqxSortable({ appendTo : string });
    ```* 
*   归还房产的*附件。

    ```html
    var appendTo = $('Selector').jqxSortable('appendTo');
    ```* 

**链接文件:**从给定链接下载 **jQWidgets** 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link type="”text/css”" rel="”Stylesheet”" href="”jqwidgets/styles/jqx.base.css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/globalize . js

**示例:**以下示例说明了 jQWidgets 中的 jqxSortable *appendTo* 属性。

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
            src="jqwidgets/globalization/globalize.js"></script>
    <script type="text/javascript" 
            src="jqwidgets/jqxsortable.js"></script>
</head>

<body>
    <h1 style="color:green">
          GeeksforGeeks 
    </h1>
    <h3>jQWidgets jqxSortable appendTo property</h3>
    <div id="sortable">
        <div><li>C</li></div>
        <div><li>C++</li></div>
        <div><li>Python</li></div>
        <div><li>HTML</li></div>
        <div><li>CSS</li></div>
        <div><li>JavaScript</li></div>
    </div>    

    <script type="text/javascript">
        $(document).ready(function () {
            $("#sortable").jqxSortable({
               appendTo: document.body
            });
        });
    </script>
</body>
</html>
```

**输出:**

![](img/685fb620516efe65fbcb4b5143b11c35.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxsortable/jquery-sortable-API . htm？搜索=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxsortable/jquery-sortable-api.htm?search=)