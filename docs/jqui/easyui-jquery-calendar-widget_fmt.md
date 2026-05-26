# EasyUI jQuery日历小部件

> 哎哎哎:# t0]https://www . geeksforgeeks . org/easy ui-jquery-calendar 小部件/

EasyUI 是一个 HTML5 框架，用于使用基于 jQuery、React、Angular 和 Vue 技术的用户界面组件。它有助于构建交互式 web 和移动应用程序的功能，为开发人员节省了大量时间。

在本文中，我们将学习如何使用 jQuery 易用户界面设计日历。日历小部件显示一个月的日历，允许用户选择日期并移到下一个月或上一个月。

## jQuery Easy UI 下载

```html
https://www.jeasyui.com/download/index.php
```

## 语法

```html
<input class="easyui-calendar">
```

## 属性

*   `宽度`：日历组件的宽度。
*   `高度`：日历组件的高度。
*   `fit`：如果为真，则设置日历大小以适合其父容器。
*   `border`：定义是否显示边框。
*   `showWeek`：定义是否显示周数。
*   `weekHeader`：周数表头显示的标签。
*   `getWeekNumber`：返回周数的函数。
*   `firstDay`：定义一周的第一天。
*   `weeks`：要显示的周列表。
*   `months`：要显示的月份列表。
*   `year`：历年。
*   `month`：日历的月份。
*   `current`：当前日期。
*   `formatter`：日格式化程序功能。

## 事件

*   `onSelect`：当用户选择日期时触发。
*   `onChange`：更改日期时触发。
*   `onNavigate`：导航年和月时触发。

## 方法

*   `options`：返回选项对象。
*   `resize`：调整日历大小。
*   `moveTo`：将日历移动到指定日期。

## CDN 链接

首先，添加项目所需的 jQuery Easy UI 脚本。

```html
<!-- EasyUI 的 jQuery 库 -->
<script type="text/javascript" src="jquery.easyui.min.js"></script>
<!-- EasyUI Mobile 的 jQuery 库 -->
<script type="text/javascript" src="jquery.easyui.mobile.js"></script>
```

## HTML 示例

```html
<!doctype html>
<html>

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="initial-scale=1.0,
        maximum-scale=1.0, user-scalable=no">

    <!-- EasyUI specific stylesheets-->
    <link rel="stylesheet" type="text/css"
        href="themes/metro/easyui.css">

    <link rel="stylesheet" type="text/css"
        href="themes/mobile.css">

    <link rel="stylesheet" type="text/css"
        href="themes/icon.css">

    <!--jQuery library -->
    <script type="text/javascript" src="jquery.min.js">
    </script>

    <!--jQuery libraries of EasyUI -->
    <script type="text/javascript"
        src="jquery.easyui.min.js">
    </script>

    <!--jQuery library of EasyUI Mobile -->
    <script type="text/javascript"
        src="jquery.easyui.mobile.js">
    </script>

    <script type="text/javascript">
      $(document).ready(function (){
        $('#gfg').calendar({
          border: false
        });
      });
    </script>
</head>

<body>

    <h1>GeeksforGeeks</h1>
    <h3>EasyUI jQuery calendar widget</h3>

    <div id="gfg" style="margin-bottom:20px">
        <div class="easyui-calendar"
             style="width:250px">
        </div>
    </div>

</body>
</html>
```

## 输出

![](img/2c47e03bf8bc726a17c98e06ddec11df.png)

## 参考

http://www.jeasyui.com/documentation/