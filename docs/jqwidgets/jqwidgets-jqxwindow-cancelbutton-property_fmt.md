# jQWidgets jqxWindow cancelButton 属性

> 原文: [https://www.geeksforgeeks.org/jqwidgets-jqxwindow-cancelbutton-property/](https://www.geeksforgeeks.org/jqwidgets-jqxwindow-cancelbutton-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。`jqxWindow` 用于在应用程序中输入数据或查看信息。

`cancelButton` 属性用于设置或获取取消按钮。当按下指定的取消按钮时，窗口将关闭。

## 语法

设置 `cancelButton` 属性。

```javascript
$('#jqxWindow').jqxWindow({ cancelButton: $('#cancelButton')});
```

获取 `cancelButton` 属性:

```javascript
var cancelButton = $('#jqxWindow').jqxWindow('cancelButton');
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

下面的示例说明了 jQWidgets 中的 `jqxWindow` `cancelButton` 属性。

### HTML

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
            $('#jqxwindow').jqxWindow({
                theme: 'energyblue',
                resizable: false,
                cancelButton: $('#cancel'),
                initContent: function () {
                    $('#cancel').jqxButton({
                        width: '65px',
                        theme: 'energyblue'
                    });
                }
            });
        });
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">GeeksforGeeks</h1>
        <h3>jQWidgets jqxWindow cancelButton Property</h3>
        <input type="button" id="cancel" value="Cancel" />
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

![](img/0a4990f5c951d7311042942f4dc7a2d3.png)

**参考:** [https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm?search=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxwindow/jquery-window-api.htm?search=)