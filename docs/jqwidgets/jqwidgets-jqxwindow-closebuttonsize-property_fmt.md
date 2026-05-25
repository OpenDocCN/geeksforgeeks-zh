# jQWidgets jqxWindow closeButtonSize 属性

> 原文: [https://www.geeksforgeeks.org/jqwidgets-jqxwindow-closebuttonsize-property/](https://www.geeksforgeeks.org/jqwidgets-jqxwindow-closebuttonsize-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。`jqxWindow` 用于在应用程序中输入数据或查看信息。

*关闭按钮大小*属性用于设置或获取指定窗口的关闭按钮大小。

## 语法

设置 `closeButtonSize` 属性。

```javascript
$('#jqxWindow').jqxWindow({ closeButtonSize: 32});
```

获得 `closeButtonSize` 属性。

```javascript
var cBS = $('#jqxWindow').jqxWindow('closeButtonSize'); 
```

## 链接文件

从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

```html
<link rel="stylesheet" href="jqwidgets/styles/jqx.base.css" type="text/css">
<link rel="stylesheet" href="jqwidgets/styles/jqx.energyblue.css" type="text/css">
<script type="text/javascript" src="scripts/jquery-1.10.2.min.js"></script>
<script type="text/javascript" src="jqwidgets/jqxcore.js"></script>
```

## 示例

以下示例说明了 jQWidgets 中的 `jqxWindow` `closeButtonSize` 属性。在下面的例子中， `closeButtonSize` 已经设置为 6。

### HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <link rel="stylesheet" href=
    "jqwidgets/styles/jqx.energyblue.css" type="text/css" />
    <script type="text/javascript" 
        src="scripts/jquery-1.10.2.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxwindow.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxbuttons.js"></script>

<script type="text/javascript">
        $(document).ready(function () {
            $("#jqxwindow").jqxWindow({
                height: 100,
                width: 300,
                theme: 'energyblue',
                position: 'center',
                closeButtonSize: 6
            });
        });
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;"> 
            GeeksforGeeks 
        </h1>

<h3>jQWidgets jqxWindow closeButtonSize Property</h3>

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

## 输出

![](img/fdb6701163699d7e67fef31a97315bc5.png)

## 参考

[https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm?search=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm?search=)