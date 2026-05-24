# jQWidgets jqxResponsivePanel collapse 断点属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxresponsevepanel-collapse 断点-property/](https://www.geeksforgeeks.org/jqwidgets-jqxresponsivepanel-collapsebreakpoint-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxResponsivePanel 是一个 jQuery 小部件，用于表示具有响应行为的面板小部件。响应面板用于以响应方式显示内容。当浏览器窗口的宽度小于设定值时，此面板折叠，单击按钮后，我们可以访问该值。

**折叠断点属性**用于设置或返回改变浏览器宽度后面板是否显示/隐藏。它接受数字类型的值，默认值为 1000。

**语法:**

*   设置 collapse 断点属性。

    ```html
    $('selector').jqxResponsivePanel({ 
        collapseBreakpoint: Number 
    });
    ```

*   返回 collapse 断点属性。

    ```html
    var collapseBreakpoint = $('selector')
        .jqxResponsivePanel('collapseBreakpoint');
    ```

**链接文件:**从链接 https://www.jqwidgets.com/download/.下载 jQWidgets 在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型= " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqxcore . js "></脚本类型>
> <脚本类型= " text/JavaScript " src = " jqwidgets/jqx-all . js

下面的例子说明了 jQWidgets 中的 jqxResponsivePanel 断点属性。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" 
          href="jqwidgets/styles/jqx.base.css" 
          type="text/css" />
    <script type="text/javascript" 
            src="scripts/jquery-1.11.1.min.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqx-all.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxresponsivepanel.js">
    </script>

    <style>
        h1,
        h3 {
            text-align: center;
        }

        #GFG {
            width: inherit;
            margin: 0 auto;
        }
    </style>
</head>

<body>
    <h1 style="color: green;">
        GeeksforGeeks
    </h1>

    <h3>
        jQWidgets jqxResponsivePanel 
        collapseBreakpoint Property
    </h3>

    <div id="GFG" style="padding: 50px;">
        <div id="TRP"></div>

        <div id="jqxRP" style="padding: 5px;">
            <h4>HTML</h4>
            <p>
                HTML stands for HyperText Markup 
                Language. It is used to design 
                web pages using a markup language. 
                HTML is the combination of Hypertext 
                and Markup language. Hypertext 
                defines the link between the web pages.
            </p>

        </div>
    </div>

    <script type="text/javascript">
        $(document).ready(function() {
            $('#jqxRP').jqxResponsivePanel({
                width: 400,
                height: 250,
                toggleButton: $('#TRP'),
                collapseBreakpoint: 500
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/a96a7e80bdf2e045656d9429befd338e.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxresponsivepanel/jquery-responsive-panel-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxresponsivepanel/jquery-responsive-panel-api.htm)