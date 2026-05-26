# jQuery 界面可选取消选项

> 原文:[https://www . geesforgeks . org/jquery-ui-可选-取消-选项/](https://www.geeksforgeeks.org/jquery-ui-selectable-cancel-option/)

jQuery UI 由 GUI 小部件、视觉效果和使用 Query JavaScript 库实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。它可以用来构建高度交互的 web 应用程序，也可以用来轻松添加小部件。

**jQuery UI 可选取消选项**用于防止在匹配元素上开始选择。

**语法:**

**用取消选项初始化可选元素:**

```html
$(".selector").selectable({
    cancel: ".cancel"
});
```

**初始化后设置或返回取消选项:**

```html
// Set the cancel option
$( ".selector" ).selectable( 
    "option", "cancel", "a,.cancel" );

// Return the cancel option
var cancel = $( ".selector" )
    .selectable( "option", "cancel" );
```

**CDN 链接:**首先，添加项目所需的 jQuery UI 脚本。

> <link rel="”stylesheet”" href="”//code.jquery.com/ui/1.12.1/themes/smoothness/jquery-ui.css”">
> <脚本 src =//code . jquery . com/jquery-1 . 12 . 4 . js "></脚本>
> <脚本 src =//code . jquery . com/ui/1 . 12 . 1/jquery-ui . js "></脚本>

**示例:**

## 超文本标记语言

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <link rel="stylesheet" href=
"//code.jquery.com/ui/1.12.1/themes/smoothness/jquery-ui.css">
    <script src="//code.jquery.com/jquery-1.12.4.js"></script>
    <script src="//code.jquery.com/ui/1.12.1/jquery-ui.js"></script>

    <style>
        h1 {
            color: green;
        }

        #list .ui-selecting {
            background: greenyellow;
        }

        #list .ui-selected {
            background: green;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h3>jQuery UI Selectable cancel Option</h3>

    <ul id="list">
        <li>Data Structure</li>
        <li>Algorithm</li>
        <li>C++</li>
        <li>Java</li>
        <li id="GFG1">HTML</li>
        <li id="GFG2">Bootstrap</li>
        <li>PHP</li>
    </ul>

    <script>
        $("#list").selectable({
            cancel: "#GFG1, #GFG2"
        });
    </script>
</body>

</html>
```

**输出:**

![](img/2a5626ee11ce4125a7c4a3a3ee186e6c.png)

**参考:**T2】https://api.jqueryui.com/selectable/#option-cancel