# 如何使用 jQuery Simone Plugin 设计窗口管理器？

> 原文:[https://www . geesforgeks . org/how-design-window-manager-using-jquery-simone-plugin/](https://www.geeksforgeeks.org/how-to-design-window-manager-using-jquery-simone-plugin/)

在本文中，我们将学习使用完全基于 HTML、JavaScript 和 jQuery 的 **Simone** 插件来设计窗口管理器。它为单个网页应用程序提供了简单的类似桌面的功能。

在下面的代码实现之前，从[官方网站](https://github.com/cezarykluczynski/simone)下载预编译文件。请注意项目目录中正确的文件路径。

**示例 1:** 下面的代码演示了带有默认选项窗口的基本任务栏。

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="UTF-8">
    <script src="../common/libs.js"></script>
    <style>
        p {
            padding: 20px 20px;
        }
    </style>
</head>

<body class="no-top-bar">
    <script class="demo-js">
        $(document).ready(function () {
            "use strict";

            // Taskbar has to be created first
            $(".taskbar").taskbar();

            // Window is binded to taskbar widget,
            // so it has to be created second
            $(".window").window();
        });
    </script>

    <div class="demo-html">
        <div class="taskbar"></div>
        <div class="window"></div>

        <div class="demo">
            <div class="description">
                <p style="text-align:center">
                    This demonstrates the basic
                    taskbar and one window,
                    both with default options.
                </p>

            </div>
        </div>
    </div>
</body>

</html>
```