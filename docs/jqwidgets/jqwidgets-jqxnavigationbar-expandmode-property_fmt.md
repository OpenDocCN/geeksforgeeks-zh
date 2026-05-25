# jqwidgets jqxnnavigator 扩展模式属性

> 原文: [https://www.geeksforgeeks.org/jqwidgets-jqxnavigationbar-expandmode-property/](https://www.geeksforgeeks.org/jqwidgets-jqxnavigationbar-expandmode-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。`jqxNavigationBar` 用于表示包含标题和内容部分的 jQuery 小部件。单击标题，内容将相应地展开或折叠。

`expandMode` 属性用于设置或获取指定 `jqxNavigationBar` 的扩展模式。此属性接受一些值，包括 `"single"`、`"singleHeight"`、`"multiple"`、`"toggle"` 和 `"none"`。

## 语法

用于设置 `expandMode` 属性:

```javascript
$('Selector').jqxNavigationBar({ 
    expandMode: "toggle" 
});  
```

获取 `expandMode` 属性:

```javascript
var expandMode = 
    $('Selector').jqxNavigationBar('expandMode');
```

## 链接文件

从给定链接下载 [jQWidgets](https://www.jqwidgets.com/download/)。在 HTML 文件中，找到下载文件夹中的脚本文件。

```html
<link rel="stylesheet" href="jqwidgets/styles/jqx.base.css" type="text/css">
<script type="text/javascript" src="scripts/jquery.js"></script>
<script type="text/javascript" src="jqwidgets/jqxcore.js"></script>
<script type="text/javascript" src="jqwidgets/jqxexpander.js"></script>
```

## 示例

下面的示例说明了 jQWidgets `jqxNavigationBar` 的 `expandMode` 属性。在下面的例子中，`expandMode` 属性的值被设置为 `"toggle"`。

### 超文本标记语言

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
            src="jqwidgets/jqxexpander.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxnavigationbar.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>
        <h3>
            jQWidgets jqxNavigationBar expandMode Property
        </h3>
        <div id="jqx_Navigation_Bar" 
             style="margin: 25px;" 
             align="left">
            <div>First Header</div>
            <div>
                <h8>Content for the first header</h8>
                <ul>
                    <li>GFG</li>
                    <li>CSE</li>
                </ul>
            </div>
            <div> Second Header</div>
            <div>
                <h8>Content for the second header</h8>
                <ul>
                    <li>GeeksforGeeks</li>
                    <li>CSE</li>
                </ul>
            </div>
        </div>
        <input type="button" style="margin: 29px;" 
               id="jqxbutton_for_expandMode"
            value="Value of the expandMode property"/>
        <div id="log"></div>
        <script type="text/javascript">
            $(document).ready(function () {
                $("#jqx_Navigation_Bar").
                    jqxNavigationBar({
                        width: 250,
                        height: 132,
                        expandMode: 'toggle'
                    });
                $("#jqxbutton_for_expandMode").
                    jqxButton({
                        width: 250,
                    });
                $('#jqxbutton_for_expandMode').
                    on('click', function () {
                        var value_of_expandMode =
                            $('#jqx_Navigation_Bar').
                                jqxNavigationBar(
                                    'expandMode');
                        $("#log").html(JSON.stringify(
                            value_of_expandMode))
                    });
            });
        </script>
    </center>
</body>

</html>
```

## 输出

![](img/8665c3e7df7ddb04a6d32af7d25bba4c.png)

## 参考

[https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-api.htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxnavigationbar/jquery-navigationbar-api.htm)