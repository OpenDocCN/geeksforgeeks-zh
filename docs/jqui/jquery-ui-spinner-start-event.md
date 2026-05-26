# jQuery 用户界面微调器启动事件

> 原文:[https://www . geesforgeks . org/jquery-ui-spinner-start-event/](https://www.geeksforgeeks.org/jquery-ui-spinner-start-event/)

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQueryUI 微调器小部件帮助我们使用上下箭头来增加和减少输入元素的值。在本文中，我们将看到如何在 jQuery UI 滑块中使用**启动** **事件**。当在 jQuery 用户界面微调器中的旋转之前被触发时，**开始** **事件**被触发。

**语法:**

```html
$( ".selector" ).spinner({
   start: function( event, ui ) {}
});
```

**CDN 链接:**首先，添加 jQuery UI 脚本 CDN 链接，这是您的任务所需要的。

> <link href="“https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css”" rel="“stylesheet”">

下面的例子说明了 jQuery UI Spinner 启动事件。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8" />
        <link href=
"https://code.jquery.com/ui/1.10.4/themes/ui-lightness/jquery-ui.css" 
              rel="stylesheet" />
        <script src=
"https://code.jquery.com/jquery-1.10.2.js">
        </script>
        <script src=
"https://code.jquery.com/ui/1.10.4/jquery-ui.js">
        </script>

        <style type="text/css">
            #gfg input {
                width: 100px;
            }
        </style>

        <script>
            $(function () {
                $("#gfg").spinner({
                    start: function (event, ui) {
                        console.log("started");
                    },
                });
            });
        </script>
    </head>

    <body>
        <h1>GeeksforGeeks</h1>
        <h2>jQuery UI | spinner start event</h2>
        <input id="gfg" />
    </body>
</html>
```

**输出:**

![](img/3e6012fc194f8d1aef4c8f606c3787cf.png)

**参考:**T2】https://api.jqueryui.com/spinner/#event-start