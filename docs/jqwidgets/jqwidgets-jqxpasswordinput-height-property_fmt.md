# jQWidgets jqxPasswordInput height Property

> 原文: [https://www.geeksforgeeks.org/jqwidgets-jqxpasswordinput-height-property/](https://www.geeksforgeeks.org/jqwidgets-jqxpasswordinput-height-property/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。`jqxPasswordInput` 是一个 jQuery 小部件，它支持输入字段密码，并对密码的强度有很好的视觉反馈。

`height` 属性用于设置或返回 `jqxPasswordInput` 小部件的高度。它接受数字/字符串类型的值，默认值为 "auto"。

## 语法

设置 `height` 属性。

```javascript
$('selector').jqxPasswordInput({ height: Boolean });
```

返回 `height` 属性。

```javascript
var height = $('selector').jqxPasswordInput('height');
```

## 链接文件

从链接下载 [jQWidgets](https://www.jqwidgets.com/download/)。在 HTML 文件中，找到下载文件夹中的脚本文件。

```html
<link rel="stylesheet" href="jqwidgets/styles/jqx.base.css" type="text/css" />
<script type="text/javascript" src="scripts/jquery-1.11.1.min.js"></script>
<script type="text/javascript" src="jqwidgets/jqxcore.js"></script>
<script type="text/javascript" src="jqwidgets/jqx-all.js"></script>
```

## 示例

以下示例说明了 jQWidgets 中的 `jqxPasswordInput` `height` 属性。

### HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <script type="text/javascript" 
        src="scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxpasswordinput.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>
        <h3>
            jQWidgets jqxPasswordInput height Property
        </h3>
        <input type="password" id="input" />
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#input").jqxPasswordInput({
                width: 300,
                height: 40,
                placeHolder: "Enter a Password"
            });
        });
    </script>
</body>

</html>
```

## 输出

![](img/697a25e49a1a4779bdf93b49871a506c.png)

## 参考

[https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxpasswordinput/jquery-password-input-getting-started.htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxpasswordinput/jquery-password-input-getting-started.htm)