# jQWidgets jqxNotification 刷新()方法

> 原文:[https://www . geesforgeks . org/jqwidgets-jqxnotification-refresh-method/](https://www.geeksforgeeks.org/jqwidgets-jqxnotification-refresh-method/)

**jQWidgets** 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大和优化的框架，独立于平台，并得到广泛支持。 **jqxNotification** 代表一个 jQuery 小部件，可以用来向用户显示一些通知内容。jqxNotification 小部件内容可以根据用户需求进行修改。

**刷新()方法**用于刷新通知。它不接受任何参数，也不返回值。

**语法:**

```html
$('Selector').jqxNotification('refresh');
```

**链接文件:**从链接下载 https://www.jqwidgets.com/download/。在 HTML 文件中，找到下载文件夹中的脚本文件:

> <link rel="”stylesheet”" href="”jqwidgets/styles/jqx.base.css”" type="”text/css”">
> <脚本类型=【文本/JavaScript】src =【脚本/jquery-1 . 11 . 1 . min . js】></脚本>
> T8】脚本类型=【文本/JavaScript】src =【jqwidgets/jqxcore . js】></脚本>
> T12】脚本类型=【文本/JavaScript】src =【jqwidgets/jqxnotification . js】

**示例:**以下示例说明了 jQWidgets 中的 jqxNotification refresh()方法:

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" 
          href="jqwidgets/styles/jqx.base.css" 
            type="text/css" />
    <script type="text/javascript" 
              src="scripts/jquery-1.11.1.min.js"> 
    </script>
    <script type="text/javascript" 
              src="jqwidgets/jqxcore.js"> 
    </script>
    <script type="text/javascript" 
              src="jqwidgets/jqxnotification.js"> 
    </script>
</head>

<body>
    <h1 style="color: green">
      GeeksforGeeks
    </h1>
    <h3>jQWidgets jqxNotification refresh() method</h3>
    <div id="not">
        Notification
    </div>

    <button id='gfg'>Click Here</button>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#not").jqxNotification({
                position: "center",
                opacity: 0.8,
                autoOpen: true,
                autoClose: false,
                template: "info",
            });
        });

        $('#gfg').click(function () {
            $("#not").jqxNotification("refresh");
            alert('Refreshed');
        });
    </script>
</body>

</html>
```

**输出:**

![](img/cf347f974fa51e6f2881baeef4302cf5.png)

**参考:**[**https://www . jqwidgets . com/jquery-widgets-documentation/documentation/jqxnotification/jquery-notification-API . htm？搜索=**](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxnotification/jquery-notification-api.htm?search=)