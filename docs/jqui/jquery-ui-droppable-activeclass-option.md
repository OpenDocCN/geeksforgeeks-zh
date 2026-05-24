# jquery ui drop active class option

> 哎哎哎:# t0]https://www . geeksforgeeks . org/jquery-ui-drop pable-active class 选项/

jQuery UI 由 GUI 小部件、视觉效果和使用 jQuery、CSS 和 HTML 实现的主题组成。jQuery 用户界面非常适合为网页构建用户界面。jQuery UI 可拖放*活动类*选项用于在拖动可接受的可拖动对象时添加将要添加到可拖放对象中的类。

**语法:**

```html
$( ".selector" ).droppable({
  activeClass: "ui-state-highlight"
});
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

        div {
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
        }

        #div2 {
            width: 150px;
            height: 150px;
            background: blue;
        }

        #div1 {
            position: absolute;
            left: 250px;
            width: 200px;
            height: 200px;
            background: green;
            color: #fff;
        }
    </style>
</head>

<body>
    <h1>GeeksforGeeks</h1>

    <h3>jQuery UI Droppable activeClass Option</h3>

    <div id="div1">Drop here</div>
    <div id="div2">Drag me</div>

    <script>
        $("#div2").draggable();
        $("#div1").droppable({
            activeClass: "ui-state-highlight"
        });
    </script>
</body>

</html>
```

**输出:**

![](img/771eca2170f11d895a8d36a3c5943661.png)

可删除的活动类选项

**参考:**[https://API . jquery ui . com/drop pable/# option-active class](https://api.jqueryui.com/droppable/#option-activeClass)