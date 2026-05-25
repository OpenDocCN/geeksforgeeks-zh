# jQuery 用户界面微调器类选项

> 原文: [https://www.geeksforgeeks.org/jquery-ui-spinner-classes-option/](https://www.geeksforgeeks.org/jquery-ui-spinner-classes-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 HTML、CSS 和 jQuery 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI 微调器类选项用于添加一些额外的类，以将样式添加到微调器元素中。

**语法:**

```html
$( ".selector" ).spinner({
  classes:
   {
    "ui-spinner": "highlight"
   }
});
```

**CDN 链接:** 首先，添加项目所需的 jQuery UI 脚本。

> ```html
> <link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/smoothness/jquery-ui.css">
> <script src="//code.jquery.com/jquery-1.12.4.js"></script>
> <script src="//code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
> ```

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <link rel="stylesheet" href=
    "//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
    <script 
        src="https://code.jquery.com/jquery-1.12.4.js">
    </script>
    <script 
        src="https://code.jquery.com/ui/1.12.1/jquery-ui.js">
    </script>

<style>
        .highlight
        {
            color: white;
            background: green;
        }
    </style>

<script>
        $(function () {
            $("#gfg").spinner({
                classes:
                {
                    "ui-spinner": "highlight"
                }
            });
        });
    </script>
</head>

<body>
    <h1 style="color: green;">GeeksforGeeks</h1>
    <h2>jQuery UI spinner classes option</h2>

<div id="geeks">
        <input type="text" id="gfg" value="45" />
    </div>
</body>

</html>
```

**输出:**

![](img/064c669d83b752f25dcb2410d298cc88.png)

微调器类

**参考:** [https://api.jqueryui.com/spinner/#option-classes](https://api.jqueryui.com/spinner/#option-classes)