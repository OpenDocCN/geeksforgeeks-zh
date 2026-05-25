# Easy UI jQuery Tooltip Widget

> 哎哎哎:# t0]https://www . geeksforgeeks . org/easy ui-jquery 工具提示小部件/

在本文中，我们将学习如何使用 jQuery EasyUI 设计工具提示小部件。EasyUI 是一个 HTML5 框架，用于使用基于 jQuery、React、Angular 和 Vue 技术的用户界面组件。它有助于构建交互式 web 和移动应用程序的功能，为开发人员节省了大量时间。

## 下载 jQuery 的 EasyUI

```html
https://www.jeasyui.com/download/index.php
```

## 语法

```javascript
var a = $(".selector").tooltip({

});
```

## 属性

*   `position`: 该属性为工具提示位置。
*   `content`: 该属性为工具提示内容。
*   `trackMouse`: 该属性使工具提示能够随鼠标移动。
*   `deltaX`: 这个属性是距离工具提示位置的水平距离。
*   `deltaY`: 该属性是工具提示位置的垂直距离。
*   `showEvent`: 该属性使工具提示出现。
*   `hideEvent`: 该属性使工具提示消失。
*   `showDelay`: 这个属性是显示工具提示的时间延迟。
*   `hideDelay`: 这个属性是隐藏工具提示的时间延迟。

## 方法

*   `destroy()`: 此方法破坏工具提示。
*   `reposition()`: 此方法重置工具提示位置。
*   `update()`: 此方法更新工具提示内容。
*   `hide()`: 此方法隐藏工具提示。
*   `show()`: 此方法显示工具提示。
*   `arrow()`: 此方法返回箭头对象。
*   `tip()`: 此方法返回提示对象。
*   `options()`: 返回选项属性。

## 事件

*   `onDestroy`: 当工具提示被破坏时，此事件会触发。
*   `onPosition`: 当工具提示位置改变时，此事件触发。
*   `onUpdate`: 工具提示内容更新时触发此事件。
*   `onHide`: 隐藏工具提示时触发此事件。
*   `onShow`: 当工具提示显示时，该事件触发。

## CDN 链接

首先，添加项目所需的 jQuery Easy UI 脚本。

```html
<!-- jQuery library for EasyUI -->
<script type="text/javascript" src="jquery.easyui.min.js"></script>
<!-- jQuery library for EasyUI Mobile -->
<script type="text/javascript" src="jquery.easyui.mobile.js"></script>
```

## 示例

### HTML

```html
<!doctype html>
<html>

<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="initial-scale=1.0, maximum-scale=1.0,
                   user-scalable=no">

    <!-- EasyUI specific stylesheets-->
    <link rel="stylesheet" type="text/css"
          href="themes/metro/easyui.css">

    <link rel="stylesheet" type="text/css"
          href="themes/mobile.css">

    <link rel="stylesheet" type="text/css"
          href="themes/icon.css">

    <!-- jQuery library -->
    <script type="text/javascript" src="jquery.min.js">
    </script>

    <!-- jQuery libraries of EasyUI -->
    <script type="text/javascript"
            src="jquery.easyui.min.js">
    </script>

    <!-- jQuery library of EasyUI Mobile -->
    <script type="text/javascript"
            src="jquery.easyui.mobile.js">
    </script>

    <h1>GeeksforGeeks</h1>
    <h3>Easy UI | tooltip widget</h3>
</head>

<body>
    <a href="#" title="This is the tooltip message."
       class="easyui-tooltip">
          Hover me
    </a>
</body>
</html>
```

## 输出

![](img/0ee4376c12b4bbb13fa60f091876d3ef.png)

## 参考

`http://www.jeasyui.com/documentation/`