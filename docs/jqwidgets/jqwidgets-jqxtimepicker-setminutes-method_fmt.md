# jQWidgets jqxTimePicker setMinutes()方法

> 原文: [https://www.geeksforgeeks.org/jqwidgets-jqxtimepicker-setminutes-method/](https://www.geeksforgeeks.org/jqwidgets-jqxtimepicker-setminutes-method/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。`jqxTimePicker` 代表一个 jQuery 小部件，用于以小时和分钟格式选择时间。

`setMinutes()` 方法用于设置分钟时间。它接受数字类型的单参数 `minute`，并且不返回任何值。

## 语法

```javascript
$('Selector').jqxTimePicker('setMinutes', minute_time);
```

## 链接文件

从给定的链接 [https://www.jqwidgets.com/download/](https://www.jqwidgets.com/download/) 下载 jQWidgets。在 HTML 文件中，找到下载文件夹中的脚本文件。

```html
<link rel="stylesheet" href="jqwidgets/styles/jqx.base.css" type="text/css" />
<script type="text/javascript" src="scripts/jquery-1.11.1.min.js"></script>
<script type="text/javascript" src="jqwidgets/jqx-all.js"></script>
<script type="text/javascript" src="jqwidgets/jqxcore.js"></script>
```

下面的例子说明了 jQWidgets jqxTimePicker `setMinutes()` 方法。

## 示例

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
        "jqwidgets/styles/jqx.base.css" type="text/css" />
    <script type="text/javascript" 
        src="scripts/jquery-1.11.1.min.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqx-all.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxcore.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxdraw.js"></script>
    <script type="text/javascript" 
        src="jqwidgets/jqxtimepicker.js"></script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>
        <h3>
            jQWidgets jqxTimePicker setMinutes() Method
        </h3>
        <div id="jqxTP"></div>
        <input type="button" value="Set Minutes" id="GFG"
            style="padding: 5px 10px; margin-top: 20px;">
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxTP").jqxTimePicker({
                width: 400,
                height: 400,
                selection: 'minute'
            });

            $("#GFG").on('click', function() {
                $('#jqxTP').jqxTimePicker('setMinutes', 24);
            });
        });
    </script>
</body>

</html>
```

## 输出

![](img/d6fd2b31a8671e1106ceb0a404e46b65.png)

## 参考

[https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtimepicker/jquery-timepicker-getting-started.htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtimepicker/jquery-timepicker-getting-started.htm)