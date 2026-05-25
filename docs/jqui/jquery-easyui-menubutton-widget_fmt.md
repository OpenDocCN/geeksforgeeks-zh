# jQuery Easy UI Menu Button Widget

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-easy ui-menu button widget/

EasyUI 是一个 HTML5 框架，用于使用基于 jQuery、React、Angular 和 Vue 技术的用户界面组件。它有助于构建交互式 web 和移动应用程序的功能，为开发人员节省了大量时间。

在本文中，我们将学习如何使用 jQuery EasyUI 设计菜单按钮。菜单按钮是下拉菜单的一部分。它与链接按钮和菜单相关联。菜单隐藏时显示链接按钮。

### jQuery 易 UI 下载:

```html
https://www.jeasyui.com/download/index.php
```

### 语法:

```html
<div class="menubutton">
</div>
```

## 属性

*   `plain`: 设置 `true` 显示素颜效果。
*   `menu`: 创建相应菜单的选择器。
*   `menuAlign`: 设置顶层菜单的对齐方式。
*   `duration`: 以毫秒为单位定义持续时间。
*   `showEvent`: 导致菜单出现的事件。
*   `hideEvent`: 导致菜单消失的事件。
*   `hasDownArrow`: 定义向下箭头图标的显示。

## 方法

*   `options()`: 返回选项对象。
*   `disable()`: 禁用菜单按钮。
*   `enable()`: 启用菜单按钮。
*   `destroy()`: 破坏菜单按钮。

### CDN 链接

首先，添加项目所需的 jQuery Easy UI 脚本。

```html
<!-- jQuery library for EasyUI -->
<script type="text/javascript" src="jquery.easyui.min.js"></script>
<!-- jQuery library for EasyUI Mobile -->
<script type="text/javascript" src="jquery.easyui.mobile.js"></script>
```

### 示例

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <meta
      name="viewport"
      content="initial-scale=1.0, 
               maximum-scale=1.0, user-scalable=no"/>

    <!-- EasyUI specific stylesheets-->
    <link rel="stylesheet" type="text/css" 
          href="themes/metro/easyui.css" />
    <link rel="stylesheet" type="text/css" 
          href="themes/mobile.css" />
    <link rel="stylesheet" type="text/css"
          href="themes/icon.css" />

    <!-- jQuery library -->
    <script type="text/javascript" 
            src="jquery.min.js">
    </script>

    <!-- jQuery libraries of EasyUI -->
    <script type="text/javascript" 
            src="jquery.easyui.min.js">
    </script>

    <!-- jQuery library of EasyUI Mobile -->
    <script type="text/javascript" 
            src="jquery.easyui.mobile.js">
    </script>

    <script type="text/javascript">
      $(document).ready(function () {
        $("#gfg").menubutton({
          disabled: true,
        });
      });
    </script>
  </head>

  <body>
    <h1>GeeksforGeeks</h1>
    <h3>EasyUI jQuery menubutton widget</h3>

    <a id="gfg" class="easyui-menubutton">Menu 1</a>
  </body>
</html>
```

### 输出

![](img/362af85fac08358401b1e017f68c2707.png)

菜单按钮

**参考:** http://www.jeasyui.com/documentation/