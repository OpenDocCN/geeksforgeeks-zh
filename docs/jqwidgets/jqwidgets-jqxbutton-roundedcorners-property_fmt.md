# jQWidgets jqxButton 圆角器属性

> 原文：[https://www.geeksforgeeks.org/jqwidgets-jqxbutton-roundedcorners-property/](https://www.geeksforgeeks.org/jqwidgets-jqxbutton-roundedcorners-property/)

## 圆角属性

`jQWidgets` 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。`jqxButton` 用于说明 jQuery 按钮小部件，它使我们能够在所需的网页上显示按钮。

`roundedCorners` 属性用于启用或禁用圆角实用程序。此外，它还影响了支持 `CSS` 边框半径的浏览器。它属于字符串类型，默认值为 `"jqx-rc-all"`。

它的可能值是：

*   `"all"`
*   `"top"`
*   `"bottom"`
*   `"left"`
*   `"right"`
*   `"top-right"`
*   `"top-left"`
*   `"bottom-right"`
*   `"bottom-left"`

## 语法

设置 `roundedCorners` 属性。

```javascript
$("#jqxButton").jqxButton({ roundedCorners: 'jqx-rc-t'});
```

获取 `roundedCorners` 属性。

```javascript
var roundedCourners = $('#jqxButton').jqxButton('roundedCorners');
```

## 链接文件

从链接下载 [jQWidgets](https://www.jqwidgets.com/download/)。在 HTML 文件中，找到下载文件夹中的脚本文件。

```html
<link rel="stylesheet" href="jqwidgets/styles/jqx.base.css" type="text/css" />
<script type="text/javascript" src="scripts/jquery-1.11.1.min.js"></script>
<script type="text/javascript" src="jqwidgets/jqxcore.js"></script>
<script type="text/javascript" src="jqwidgets/jqxbuttons.js"></script>
```

下面的例子说明了 `jQWidgets` 中的 `jqxButton` `roundedCorners` 属性。

## 示例

### HTML

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
            src="jqwidgets/jqxbuttons.js">
    </script>
</head>

<body>
    <center>
        <h1 style="color: green">GeeksforGeeks</h1>
        <h3>jQWidgets jqxButton roundedCorners Property</h3>
        <br />
        <input type="button" id="jqxBtn" 
               style="padding: 5px 20px" 
               value="Click here" />
        <div id="log"></div>
    </center>

    <script type="text/javascript">
        $(document).ready(function () {
            $("#jqxBtn").jqxButton({
                width: "100px",
                height: "60px",
                roundedCorners: "top",
            });

            $("#jqxBtn").on("click", function (event) {
                var rc = $("#jqxBtn")
                    .jqxButton("roundedCorners");
                $("#log").html("value: " + rc);
            });
        });
    </script>
</body>

</html>
```

## 输出

![](img/ba18880c4a3e68ca4f0fca4bcdb75db6.png)

## 参考

[https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-api.htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxbutton/jquery-button-api.htm)