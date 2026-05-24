# jQWidgets jqxlloader 自动打开属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxloader-auto open-property/](https://www.geeksforgeeks.org/jqwidgets-jqxloader-autoopen-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxLoader 代表一个显示内置加载器元素的 jQuery 小部件。加载程序可以包含图标或文本，或者图标和文本的组合。加载器元素可以被加载，直到小部件的数据被加载。

**自动打开**属性用于设置或返回创建后的加载程序。它接受布尔类型值，默认值为 false。

**语法:**

设置*自动打开*属性。

```html
$('selector').jqxLoader({ autoOpen: Boolean });
```

返回*自动打开*属性。

```html
var autoOpen = $('selector').jqxLoader('autoOpen');
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/.) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> < link rel= "样式表" href = " jqwidgets/style/jqx . energy blue . CSS " type = " text/CSS "/>
> <script type = " text/JavaScript " src = " scripts/jquery-1 . 11 . 1 . min . js "></script>
> <script type = " text/JavaScript " src = " jqwidgets/jqxcore . js

下面的例子说明了 jQWidgets jqxlloader*自动打开*属性。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" 
          type="text/css" />
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.energyblue.css" 
          type="text/css" />
    <script type="text/javascript" 
        src="scripts/jquery-1.11.1.min.js">
    </script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
        src="jqwidgets/jqxloader.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxLoader autoOpen Property
        </h3>

        <div id="jqxLoader"></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxLoader").jqxLoader({
                width: 300,
                height: 200,
                autoOpen: true
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/61e03b36181868b4f9da27fa70e92526.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxloader/jquery-loader-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxloader/jquery-loader-api.htm)