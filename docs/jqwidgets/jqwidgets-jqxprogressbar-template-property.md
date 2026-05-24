# jQWidgets jqxProgressBar 模板属性

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxprogressbar-template-property/](https://www.geeksforgeeks.org/jqwidgets-jqxprogressbar-template-property/)

**简介:jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。jqxProgressBar 用于表示 jQuery 进度条小部件，它直观地指示冗长操作的进度。

*模板*属性用于设置或返回模板，作为默认样式的替代。它接受字符串类型值，其默认值为“默认值”。

它的可能值如下

*   **default:**是默认模板，其样式取决于“主题”属性值。
*   **【初级】:**设置深蓝色风格，增加视觉重量。
*   **“成功”:**它为成功或积极的行动设置绿色风格。
*   **“警告”:**设置代表警告的橙色样式。
*   **“危险”:**设置代表危险或消极动作的红色样式。
*   **【信息】:**设置蓝色按钮，不绑定语义动作或使用。

**语法:**

设置*模板*属性。

```html
$('selector').jqxProgressBar({ template: String });
```

返回*模板*属性。

```html
var template = $('selector').jqxProgressBar('template');
```

**链接文件:**从链接下载 [jQWidgets](https://www.jqwidgets.com/download/) 。在 HTML 文件中，找到下载文件夹中的脚本文件。

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">

**示例:**以下示例说明了 jQWidgets 中的 jqxProgressBar *模板*属性

## 超文本标记语言

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
        src="jqwidgets/jqxprogressbar.js"></script>

    <style>
        h1,
        h3 {
            text-align: center;
        }

        #jqxPB {
            margin-left: 40%;
        }
    </style>
</head>

<body>
    <h1 style="color: green;">
        GeeksforGeeks
    </h1>

    <h3>
        jQWidgets jqxProgressBar template Property
    </h3>

    <div id='jqxPB'></div>

    <script type="text/javascript">
        $(document).ready(function() {
            $("#jqxPB").jqxProgressBar({
                value: 60,
                width: 250,
                height: 30,
                template: 'success'
            });
        });
    </script>
</body>

</html>
```

**输出:**

![](img/586afb7cb3173200a3656e0a11481861.png)

**参考:**[https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxprogressbar/jquery-progressbar-API . htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxprogressbar/jquery-progressbar-api.htm)