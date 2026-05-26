# easy ui jquery date box widget

> 哎哎哎:# t0]https://www . geeksforgeeks . org/easy ui-jquery-datetimebox 小部件/

EasyUI 是一个 HTML5 框架，用于使用基于 jQuery、React、Angular 和 Vue 技术的用户界面组件。它有助于构建交互式 web 和移动应用程序的功能，为开发人员节省了大量时间。

在本文中，我们将学习如何使用 jQuery EasyUI 设计一个 datetimebox。datetimebox 小部件是一个日历，可以访问日期、月份、年份和时间。

**jQuery 易 UI 下载:**

```html
https://www.jeasyui.com/download/index.php
```

**语法:**

```html
<input class="easyui-datetimebox">
```

**属性:**

*   **当前文本:**当天按钮显示的文本。
*   **关闭文本:**关闭按钮显示的文本。
*   **确定文本:**确定按钮显示的文本。
*   **spinnerWidth:** 嵌入到 datetimebox 中的 timespinner 组件的宽度。
*   **显示秒:**定义是否显示第二条信息。
*   **小时 12:** 定义是否以 12 小时格式显示时间。
*   **时间分隔符:**小时、分钟和秒之间的时间分隔符。

**方法:**

*   **选项:**返回选项对象。
*   **微调器:**返回 timespinner 对象。
*   **设置值:**设置日期时间框值。
*   **克隆来自:**从源日期时间框克隆日期时间框。

**CDN 链接:**首先，添加项目所需的 jQuery Easy UI 脚本。

**例 1:**

## 超文本标记语言

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
        $('#gfg').datetimebox({ 
           closeText: 'close',
           okText: 'open'
        }); 
      }); 
    </script> 
</head> 

<body>

    <h1>GeeksforGeeks</h1>
    <h3>EasyUI jQuery datetimebox widget</h3>

    <input id="gfg" class="easyui-datetimebox">

</body>
</html>
```

**输出:**

![](img/3fb397521727fcdc27c7e42f522fc97f.png)

**参考:**T2】http://www.jeasyui.com/documentation/