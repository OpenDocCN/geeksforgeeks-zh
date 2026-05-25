# jQWidgets jqxScrollBar 值属性

> 原文: [https://www.geeksforgeeks.org/jqwidgets-jqxscrollbar-value-property/](https://www.geeksforgeeks.org/jqwidgets-jqxscrollbar-value-property/)

`jQWidgets` 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。`jqxScrollBar` 用于表示 jQuery 小部件，该部件提供了一个滚动条，该滚动条具有一个滑动的拇指，其位置对应于一个值。

`value` 属性用于设置或获取指定 `jqxScrollBar` 的值。

## 语法

*   设置 `value` 属性:

```javascript
$('#jqxScrollBar').jqxScrollBar({ value: 300 });
```

*   要获取 `value` 属性:

```javascript
var value = $('#jqxScrollBar').jqxScrollBar('value');
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

下面的示例说明了 `jQWidgets` `jqxScrollBar` `value` 属性。在以下示例中，`value` 属性的值已设置为 500。

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
            jQWidgets jqxScrollBar value Property
        </h3>
        <div id='jqx_Scroll_Bar'></div>
        <input type="button" style="margin: 28px;" 
               id="button_for_value" 
               value="Value of the value property"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Scroll_Bar").jqxScrollBar({
                    width: 300,
                    height: 20,
                    value: 500
                });
                $("#button_for_value").jqxButton({
                    width: 250
                });
                $("#button_for_value").jqxButton().click(function () 
                   {
                        var Value_of_value =
                            $('#jqx_Scroll_Bar').jqxScrollBar('value');
                        $("#log").html((Value_of_value));
                    });
            });
        </script>
    </center>
</body>

</html>
```

## 输出

![](img/356a33344381d7edc5c291ccfa097969.png)

## 参考

[https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxscrollbar/jquery-scrollbar-api.htm?search=](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxscrollbar/jquery-scrollbar-api.htm?search=)