# 如何使用 jQuery Mobile 创建基本的弹出按钮？

> 原文:[https://www . geeksforgeeks . org/如何使用-jquery-mobile/](https://www.geeksforgeeks.org/how-to-create-a-basic-popup-button-using-jquery-mobile/) 创建基本弹出按钮

jQuery Mobile 是一种基于网络的技术，用于制作可在所有智能手机、平板电脑和台式机上访问的响应内容。在本文中，我们将使用 jQuery Mobile 创建一个基本的弹出按钮。

**方法:**添加项目所需的 jQuery Mobile 脚本。

> <link rel="”stylesheet”" href="”http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css”">

我们将使用不同类型的 ui 类来制作一个简单的弹出按钮。要添加弹出窗口，我们将使用*数据-角色=“弹出窗口”*属性到 div 元素。 *data-rel=“弹出窗口”*属性用于告诉框架在点击链接时打开弹出窗口。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" href=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.css" />

    <script src=
        "http://code.jquery.com/jquery-1.11.1.min.js">
    </script>

    <script src=
"http://code.jquery.com/mobile/1.4.5/jquery.mobile-1.4.5.min.js">
    </script>
</head>

<body>
    <center>
        <h1>GeeksforGeeks</h1>

        <h4>
            Basic popup button using jQuery Mobile
        </h4>

        <a href="#basicPopup" data-rel="popup" 
            class="ui-btn ui-corner-all ui 
            shadow ui-btn-inline"
            data-transition="pop">Basic Popup</a>
        <div data-role="popup" id="basicPopup">        
            <p>It is a simple example of basic popup</p>
        </div>
    </center>
</body>

</html>
```

**输出:**

![](img/4215d53e1cb1c9a294e4ec19288a32a3.png)