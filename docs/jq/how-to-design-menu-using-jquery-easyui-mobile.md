# 如何使用 jQuery 易 UI Mobile 设计菜单？

> 原文:[https://www . geesforgeks . org/how-design-menu-use-jquery-easy ui-mobile/](https://www.geeksforgeeks.org/how-to-design-menu-using-jquery-easyui-mobile/)

在本文中，我们将学习如何使用 jQuery 易 UI Mobile 插件设计菜单列表。EasyUI 是一个 HTML5 框架，用于使用基于 jQuery、React、Angular 和 Vue 技术的用户界面组件。它有助于构建交互式 web 和移动应用程序的功能，为开发人员节省了大量时间。

**jQuery 易 UI 下载:**

```html
https://www.jeasyui.com/download/index.php
```

**示例 1:** 以下示例演示了使用 jQuery 易用户移动插件的简单菜单。

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
</head>

<body>
    <div class="easyui-navpanel" style="position:relative">

        <!-- m-title,m-toolbar class is used here-->
        <header>
            <div class="m-toolbar">
                <div class="m-title">Menu</div>
                <div class="m-right">

                    <!-- Icons taken from themes folder-->
                    <a href="javascript: void(0)" 
                        class="easyui-linkbutton"
                        data-options="iconCls: 'icon-search',
                            plain: true">
                    </a>

                    <!-- 'easyui-menubutton' class 
                        is used here-->
                    <a href="javascript:void(0)" 
                        class="easyui-menubutton" 
                        data-options="iconCls:'icon-more',
                                    menu: '#menuID',
                                   menuAlign: 'right',
                                   hasDownArrow: true">
                    </a>
                </div>
            </div>
        </header>
    </div>

    <div id="menuID" class="easyui-menu" 
        style="width:150px;">
        <div>New tab</div>
        <div>New Window</div>

        <!-- EasyUI Menu separator class -->
        <div class="menu-sep"></div>
        <div>History</div>
        <div>Bookmarks</div>
        <div>Downloads</div>

        <div class="menu-sep"></div>
        <div>Edit</div>
        <div>Cut</div>
        <div>Copy</div>
        <div>Paste</div>
        <div class="menu-sep"></div>
        <div>Settings</div>
        <div data-options="iconCls: 'icon-remove'">
            Clear
        </div>
        <div>Exit</div>
    </div>
</body>

</html>
```