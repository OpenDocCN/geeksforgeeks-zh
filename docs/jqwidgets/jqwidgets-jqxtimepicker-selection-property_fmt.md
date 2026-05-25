# jQWidgets jqxTimePicker `selection` 属性

> 原文: [https://www.geeksforgeeks.org/jqwidgets-jqxtimepicker-selection-property/](https://www.geeksforgeeks.org/jqwidgets-jqxtimepicker-selection-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。`jqxTimePicker` 代表一个 jQuery 小部件，用于以小时和分钟格式选择时间。

## `selection` 属性

`selection` 属性用于设置或返回当前是否启用小时或分钟选择。它接受字符串类型值，默认值为 `"hour"`。

它的可能值是：
*   `"hour"`
*   `"minute"`

## 语法

设置 `selection` 属性。

```javascript
$('selector').jqxTimePicker({ selection: 'minute' });
```

返回 `selection` 属性。

```javascript
var selection = $('selector').jqxTimePicker('selection');
```

## 链接文件

从给定的链接 [https://www.jqwidgets.com/download/](https://www.jqwidgets.com/download/) 下载 jQWidgets。在 HTML 文件中，找到下载文件夹中的脚本文件。

```html
<link rel="stylesheet" href="jqwidgets/styles/jqx.base.css" type="text/css" />
<script type="text/javascript" src="scripts/jquery-1.11.1.min.js"></script>
<script type="text/javascript" src="jqwidgets/jqx-all.js"></script>
<script type="text/javascript" src="jqwidgets/jqxcore.js"></script>
```

下面的例子说明了 jQWidgets `jqxTimePicker` `selection` 属性。

## 示例

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
            jQWidgets jqxTimePicker selection Property
        </h3>

        <div id="jqxTP"></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxTP").jqxTimePicker({
                width: 400,
                height: 400,
                selection: 'minute'
            });
        });
    </script>
</body>

</html>
```

### 输出

![](img/9f7253ca11ef8868e5d65d733e60ffd6.png)

### 参考

[https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtimepicker/jquery-timepicker-getting-started.htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxtimepicker/jquery-timepicker-getting-started.htm)