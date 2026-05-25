# Easy UI jQuery Checkbox Widget

> 哎哎哎:# t0]https://www . geeksforgeeks . org/easy ui-jquery checkbox widget/

在本文中，我们将学习如何使用 jQuery 易用户界面设计一个复选框。**复选框**小部件用于选择多个选项。每个选项都可以通过点击框来启用。EasyUI 是一个 HTML5 框架，用于使用基于 jQuery、React、Angular 和 Vue 技术的用户界面组件。它有助于构建交互式 web 和移动应用程序的功能，为开发人员节省了大量时间。

**jQuery 易 UI 下载:**

```html
https://www.jeasyui.com/download/index.php
```

**语法:**

```html
<input class="easyui-checkbox">
```

**属性:**

*   `width`: 用于设置复选框的宽度。
*   `height`: 用于设置复选框的高度。
*   `value`: 用于设置复选框的默认值。
*   `checked`: 用于勾选复选框。
*   `disabled`: 用于禁用复选框。
*   `label`: 复选框绑定的标签。
*   `labelWidth`: 用于设置标签宽度。
*   `labelPosition`: 用于设置标签位置。
*   `labelAlign`: 用于设置标签对齐。

**事件:**

*   `onChange`: 当检查的值改变时，它关闭。

**方法:**

*   `options`: 返回选项对象。
*   `setValue`: 设置复选框的值。
*   `disable`: 禁用复选框组件。
*   `enable`: 启用复选框组件。
*   `check`: 勾选复选框。
*   `uncheck`: 取消勾选复选框。
*   `clear`: 清零值。
*   `reset`: 复位数值。

**CDN 链接:** 首先，添加项目所需的 jQuery Easy UI 脚本。

> <!--易 UI 的 jQuery 库-->
> <script type="text/javascript" src="jquery.easyui.min.js"></script>
> <!--易 UI Mobile 的 jQuery 库-->
> <script type="text/javascript" src="jquery.easyui.mobile.js"></script>

**示例:**

## HTML

```html
<html>
<head> 
    <!-- EasyUI specific stylesheets-->
    <link rel="stylesheet" type="text/css"
          href="themes/metro/easyui.css">

    <link rel="stylesheet" type="text/css"
          href="themes/mobile.css">

    <link rel="stylesheet" type="text/css"
          href="themes/icon.css">

    <!--jQuery library -->
    <script type="text/javascript" 
            src="jquery.min.js"> 
    </script>

    <!--jQuery libraries of EasyUI -->
    <script type="text/javascript"
            src="jquery.easyui.min.js"> 
    </script>

    <!--jQuery library of EasyUI Mobile -->
    <script type="text/javascript"
            src="jquery.easyui.mobile.js"> 
    </script>
</head> 
<body>
    <h1>GeeksforGeeks</h1>
    <h3>EasyUI jQuery checkbox widget</h3>

    <form id="gfg">
        <div style="margin-bottom:10px">
            <input class="easyui-checkbox" 
                   name="language" 
                   value="HTML" 
                   label="1st:">
        </div>
        <div style="margin-bottom:10px">
            <input class="easyui-checkbox" 
                   name="language" 
                   value="JavaScript" 
                   label="2nd:">
        </div>
        <div style="margin-bottom:10px">
            <input class="easyui-checkbox" 
                   name="language"
                   value="jQuery" 
                   label="3rd:">
        </div>
    </form>
</body>
</html>
```

**输出:**

![](img/b39329702bb8df38713a932e5c5134ad.png)

**参考:** [https://www.jeasyui.com/documentation/checkbox.php](https://www.jeasyui.com/documentation/checkbox.php)