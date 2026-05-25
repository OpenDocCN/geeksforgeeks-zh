# jQWidgets jqxScrollView buttonsOffset 属性

> 原文: [https://www.geeksforgeeks.org/jqwidgets-jqxscrollview-buttonsoffset-property/](https://www.geeksforgeeks.org/jqwidgets-jqxscrollview-buttonsoffset-property/)

`jQWidgets` 是一个 JavaScript 框架，用于为 PC 和移动设备制作基于 web 的应用程序。它是一个非常强大、优化、独立于平台并且得到广泛支持的框架。`jqxScrollView` 是一个 jQuery 小部件，用于查看比设备屏幕上可见区域更宽的内容。可以使用拖动动作或点击位于 `jqxScrollView` 小部件底部的按钮来选择特定元素。

`buttonsOffset` 属性用于设置或返回小部件的 `buttonsOffset` 属性。它设置与导航按钮默认位置的偏移量。它接受数组类型值，默认值为 `[0, 0]`。

## 语法

*   设置 `buttonsOffset` 属性。

```javascript
$('selector').jqxScrollView({ buttonsOffset: Number/String });
```

*   返回 `buttonsOffset` 属性。

```javascript
var buttonsOffset = $('selector').jqxScrollView('buttonsOffset');
```

## 链接文件

从链接下载 [jQWidgets](https://www.jqwidgets.com/download/)。在 HTML 文件中，找到下载文件夹中的脚本文件。

```html
<link rel="stylesheet" href="jqwidgets/styles/jqx.base.css" type="text/css">
<script type="text/javascript" src="scripts/jquery-1.11.1.min.js"></script>
<script type="text/javascript" src="jqwidgets/jqxcore.js"></script>
<script type="text/javascript" src="jqwidgets/jqx-all.js"></script>
```

## 示例

以下示例说明了 jQWidgets 中的 jqxScrollView `buttonsOffset` 属性。

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
            src="jqwidgets/jqx-all.js">
    </script>
    <script type="text/javascript" 
            src="jqwidgets/jqxscrollview.js">
    </script>

    <style>
        h1,
        h3 {
            text-align: center;
        }

        #jqxSV {
            width: 100%;
            margin: 0 auto;
        }
    </style>
</head>

<body>
    <h1 style="color:green;">
        GeeksforGeeks
    </h1>

    <h3>
        jQWidgets jqxScrollView buttonsOffset Property
    </h3>

    <div id="jqxSV">
        <img class="photo" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211116170527/GetHired-300x121.png"
            alt="">
        <img class="photo" src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211116170612/hiring-300x115.png"
            alt="">
        <img class="photo"
            src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211116170700/upgrade-300x126.png"
            alt="">
        <img class="photo"
            src=
"https://media.geeksforgeeks.org/wp-content/uploads/20211116170745/gethiredgfg-300x110.png"
            alt="">
    </div>
    <script type="text/javascript">
        $(document).ready(function () {
            $('#jqxSV').jqxScrollView({
                width: 450,
                height: 250,
                buttonsOffset: [0, 0]
            });
        });
    </script>
</body>
</html>
```

## 输出

![](img/1678339b8b311d4bbc57f996def24e05.png)

## 参考

[https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxscrollview/jquery-scrollview-api.htm](https://www.jqwidgets.com/jquery-widgets-documentation/documentation/jqxscrollview/jquery-scrollview-api.htm)