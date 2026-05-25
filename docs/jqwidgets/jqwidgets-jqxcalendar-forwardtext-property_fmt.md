# jQWidgets jqxCalendar forwardText 属性

> 原文: [https://www.geeksforgeeks.org/jqwidgets-jqxcalendar-forwardtext-property/](https://www.geeksforgeeks.org/jqwidgets-jqxcalendar-forwardtext-property/)

jQWidgets 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。`jqxCalendar` 代表一个 jQuery 日历小部件，使用户能够使用可视的月历显示来选择日期。

`forwardText` 属性用于设置或返回当鼠标光标移动到向前导航按钮上时显示的工具提示文本。当我们将 `enableTooltips` 属性设置为真时，此属性有效。它接受字符串类型值，默认值为“前进”。

## 语法

```html
$('.selector').jqxCalendar({
  forwardText: String
});
```

## 链接文件

从 [https://www.jqwidgets.com/download/](https://www.jqwidgets.com/download/) 链接下载 jQWidgets。在 HTML 文件中，找到下载文件夹中的脚本文件:

```html
<link rel="stylesheet" href="jqwidgets/styles/jqx.base.css" type="text/css" />
<script type="text/javascript" src="scripts/jquery-1.11.1.min.js"></script>
<script type="text/javascript" src="jqwidgets/jqxcore.js"></script>
<script type="text/javascript" src="jqwidgets/jqxdatetimeinput.js"></script>
```

以下示例说明了 jQWidgets 中的 `jqxCalendar` `forwardText` 属性:

## 示例

### 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href=
"jqwidgets/styles/jqx.base.css" type="text/css" />
    <script type="text/javascript" 
            src=
"scripts/jquery-1.11.1.min.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcore.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxdatetimeinput.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxcalendar.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/globalization/globalize.js">
    </script>
    <script tyle="text/javascript" 
            src="jqwidgets/jqx-all.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green;">
            GeeksforGeeks
        </h1>

        <h3>
            jQWidgets jqxCalendar forwardText Property
        </h3>

        <div id='jqxcal'></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#jqxcal").jqxCalendar({
                width: '400px',
                height: '300px',
                enableTooltips: true,
                forwardText: "Forward-Option"
            });
        });
    </script>
</body>

</html>
```

## 输出

![](img/0291151cb151250aa0236de9b0fe88cb.png)

## 参考

[https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxcalendar/jquery-calendar-api.htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxcalendar/jquery-calendar-api.htm)