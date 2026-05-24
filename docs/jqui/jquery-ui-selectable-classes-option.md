# jQuery 用户界面可选类选项

> 原文:[https://www . geesforgeks . org/jquery-ui-selected-class-option/](https://www.geeksforgeeks.org/jquery-ui-selectable-classes-option/)

[jQuery UI](https://www.geeksforgeeks.org/jquery-ui-introduction/) 由 GUI 小部件、视觉效果和使用 [jQuery](https://www.geeksforgeeks.org/jquery-tutorials/) [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 库实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。它可以用来构建高度交互的 web 应用程序，也可以用来轻松添加小部件。

jQuery UI 可选*类*选项用于向元素动态添加一些额外的类。

**语法:**

*   **用** ***类*** **选项初始化可选元素:**

    ```html
    $(".selector").selectable({
        classes: {
            "ui-selectable": "class-name"
        }
    });
    ```

*   **初始化后设置** ***类*** **选项:**

    ```html
    $( ".selector" ).selectable( "option", 
        "classes.ui-selectable", "class-name");
    ```

*   **初始化后返回** ***类*** **选项:**

    ```html
    var classes = $( ".selector" ).selectable(
        "option", "classes.ui-selectable" );
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
    <link rel="stylesheet" 
          href=
"https/code.jquery.com/ui/1.12.1/themes/smoothness/jquery-ui.css">
    <script src=
"https/code.jquery.com/jquery-1.12.4.js">
    </script>
    <script src=
"https/code.jquery.com/ui/1.12.1/jquery-ui.js">
    </script>
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

    .GFG {
        font-size: 20px;
        font-weight: bold;
    }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>
    <h3>jQuery UI Selectable classes Option</h3>
    <ul id="list">
        <li>Data Structure</li>
        <li>Algorithm</li>
        <li>C++</li>
        <li>Java</li>
        <li>HTML</li>
        <li>Bootstrap</li>
        <li>PHP</li>
    </ul>
    <script>
        $("#list").selectable({
            classes: {
                "ui-selected": "GFG"
            }
        });
    </script>
</body>

</html>
```

**输出:**

![Selectable classes Option](img/18b9b6f05cde007ad9aea77336fe9d86.png)

**参考:**T2】https://api.jqueryui.com/selectable/#option-classes