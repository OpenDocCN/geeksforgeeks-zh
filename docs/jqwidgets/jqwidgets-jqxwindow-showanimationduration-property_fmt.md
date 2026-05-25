# jQWidgets jqxWindow showAnimationDuration 属性

> 原文: [https://www.geeksforgeeks.org/jqwidgets-jqxwindow-showanimationduration-property/](https://www.geeksforgeeks.org/jqwidgets-jqxwindow-showanimationduration-property/)

`jQWidgets` 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。`jqxWindow` 用于在应用程序中输入数据或查看信息。

`showAnimationDuration` 属性用于设置或获取指定窗口的显示动画持续时间。

## 语法

设置 `showAnimationDuration` 属性。

```javascript
$('#jqxWindow').jqxWindow({ showAnimationDuration: 200 });
```

获取 `showAnimationDuration` 属性:

```javascript
var showAnimationDuration = $('#jqxWindow').jqxWindow('showAnimationDuration');
```

## 链接文件

从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/)。在 HTML 文件中，找到下载文件夹中的脚本文件。

```html
<link rel="stylesheet" href="jqwidgets/styles/jqx.base.css" type="text/css">
<link rel="stylesheet" href="jqwidgets/styles/jqx.summer.css" type="text/css">
<script type="text/javascript" src="scripts/jquery-1.10.2.min.js"></script>
<script type="text/javascript" src="jqwidgets/jqxcore.js"></script>
```

## 示例

以下示例说明了 jQWidgets 中的 `jqxWindow` `showAnimationDuration` 属性。在本例中，`showAnimationDuration` 设置为 3000。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.summer.css" type="text/css" />
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
                autoOpen: false,
                showAnimationDuration: 3000
            });
            $("#jqxbutton").jqxButton({
                theme: 'energyblue',
                width: 200,
                height: 30
            });
            $('#jqxbutton').click(function () {
                $("#jqxwindow").jqxWindow('open')
            });
        });
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;"> GeeksforGeeks </h1>
        <h3> jQWidgets jqxWindow showAnimationDuration Property </h3>
        <input type="button" style="margin: 10px;" 
            id="jqxbutton" value="Open the below window" />
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

![](img/ace9287bebc684b43b408f64cca0fffe.png)

## 参考

[https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm?search=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm?search=)