# jQWidgets jqxScrollBar showButtons 属性

> 原文：[https://www.geeksforgeeks.org/jqwidgets-jqxscrollbar-showbuttons-property/](https://www.geeksforgeeks.org/jqwidgets-jqxscrollbar-showbuttons-property/)

`jQWidgets` 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。`jqxScrollBar` 用于表示一个 jQuery 小部件，该部件提供了一个滚动条，该滚动条具有一个滑动的拇指，其位置对应于一个值。

`showButtons` 属性用于设置或获取指定滚动条是否显示增减箭头按钮。

## 语法

用于设置 `showButtons` 属性。

```javascript
$('#jqxScrollBar').jqxScrollBar({ showButtons: true });
```

获取 `showButtons` 属性。

```javascript
var showButtons = $('#jqxScrollBar').jqxScrollBar('showButtons');
```

## 链接文件

从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/)。在 HTML 文件中，找到下载文件夹中的脚本文件。

```html
<link rel="stylesheet" href="jqwidgets/styles/jqx.base.css" type="text/css"/>
<script type="text/javascript" src="scripts/jquery.js"></script>
<script type="text/javascript" src="jqwidgets/jqxcore.js"></script>
<script type="text/javascript" src="jqwidgets/jqxbuttons.js"></script>
```

## 示例

下面的示例说明了 jQWidgets jqxScrollBar `showButtons` 属性。在下面的例子中，`showButtons` 属性的值被设置为 `true`。

### HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" 
          href="jqwidgets/styles/jqx.base.css"
          type="text/css"/>
    <script type="text/javascript" 
            src="scripts/jquery.js">
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
            src="jqwidgets/jqx-all.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color:green;">
            GeeksforGeeks
        </h1>
        <h3>
            jQWidgets jqxScrollBar showButtons Property
        </h3>
        <div id='jqx_Scroll_Bar'></div>
        <input type="button" style="margin: 28px;" 
               id="button_for_showButtons" 
               value="Value of the showButtons property"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Scroll_Bar").jqxScrollBar({
                    width: 200,
                    height: 20,
                    showButtons: true
                });
                $("#button_for_showButtons").jqxButton({
                    width: 250
                });
                $("#button_for_showButtons")
                .jqxButton().click(function () {
                    var Value_of_showButtons =
                        $('#jqx_Scroll_Bar')
                        .jqxScrollBar('showButtons');
                    $("#log").html((Value_of_showButtons));
                });
            });
        </script>
    </center>
</body>
</html>
```

**输出：**

![](img/7017791d0e03d1df8f994f45ce357199.png)

**参考：**[https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxscrollbar/jquery-scrollbar-api.htm?search=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxscrollbar/jquery-scrollbar-api.htm?search=)